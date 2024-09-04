+++
title = "2. Setup Openswan on EC2 - DC - EC2 Openswan Gateway"
weight = 2
+++


Click "Download Configuration" We will use this configuration to set up our Openswan gateway.


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/28-150477-image.png)


Select the options as shown, and click "Download"


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/28-946139-image.png)


Open that file, and you can see all the instructions. You can read it to learn more details.


For now, let’s focus on certain parts of the `IPSEC Tunnel #1` configuration, such as `conn` and `secrets`, as shown below:


```bash
---
IPSEC Tunnel #1
---
...
conn Tunnel1
	authby=secret
	auto=start
	left=%defaultroute
	leftid=54.85.149.143
	right=3.225.20.219
	type=tunnel
	ikelifetime=8h
	keylife=1h
	phase2alg=aes128-sha1;modp1024
	ike=aes128-sha1;modp1024
	auth=esp
	keyingtries=%forever
	keyexchange=ike
	leftsubnet=<LOCAL NETWORK>
	rightsubnet=<REMOTE NETWORK>
	dpddelay=10
	dpdtimeout=30
	dpdaction=restart_by_peer
...
5) Create a new file at /etc/ipsec.d/aws.secrets if it doesn't already exist, and append this line to the file (be mindful of the spacing!):
54.85.149.143 3.225.20.219: PSK "yioHTXdE29JV2HmcDpx8nXhzQwkdR5FW"
...
```


We’ll need to use these two configurations/credentials, and we will build the command to add the `conn` configuration as follows:

1. Remove `auth=esp` to avoid conflicts with the Amazon Linux 2 AMI - VPN configuration.
2. Update `leftsubnet=192.168.0.0/16` to match the current **VPC - DC** CIDR (Local).
3. Update `rightsubnet=10.10.0.0/16` to match the current VPC **VPC - AWS** CIDR (Remote).
4. Keep everything else in the configuration the same.

So my `add conn` command will look like this:


```bash
sudo bash -c 'cat <<EOF > /etc/ipsec.d/aws.conf
conn Tunnel1
  authby=secret
  auto=start
  left=%defaultroute
  leftid=54.85.149.143
  right=3.225.20.219
  type=tunnel
  ikelifetime=8h
  keylife=1h
  phase2alg=aes128-sha1;modp1024
  ike=aes128-sha1;modp1024
  keyingtries=%forever
  keyexchange=ike
  leftsubnet=192.168.0.0/16
  rightsubnet=10.10.0.0/16
  dpddelay=10
  dpdtimeout=30
  dpdaction=restart_by_peer
EOF'
cat /etc/ipsec.d/aws.conf
```


Next step, look at the remaining parts of the downloaded configuration file.


```bash
5) Create a new file at /etc/ipsec.d/aws.secrets if it doesn't already exist, and append this line to the file (be mindful of the spacing!):
54.85.149.143 3.225.20.219: PSK "yioHTXdE29JV2HmcDpx8nXhzQwkdR5FW"
```


We will build our `add secret` command by inserting the key in the middle of this command.


```bash
sudo bash -c 'cat <<EOF > /etc/ipsec.d/aws.secrets
54.85.149.143 3.225.20.219: PSK "yioHTXdE29JV2HmcDpx8nXhzQwkdR5FW"
EOF'
cat /etc/ipsec.d/aws.secrets
```


Nice! Now SSH into **DC - EC2 - Openswan Gateway** again. We will follow a series of steps to set up Openswan.


```bash
# Change to su user, we will have full permissions to run all commands
sudo su

# Install openswan
yum install openswan -y

# Edit `/etc/sysctl.conf` to avoid redirect attach
sudo bash -c 'cat <<EOF > /etc/sysctl.conf
net.ipv4.ip_forward = 1
net.ipv4.conf.all.accept_redirects = 0
net.ipv4.conf.all.send_redirects = 0
EOF'
cat /etc/sysctl.conf

# Run the `add conn command` that you just built
# This is my `add conn command` command, remember to run YOUR instead
sudo bash -c 'cat <<EOF > /etc/ipsec.d/aws.conf
conn Tunnel1
  authby=secret
  auto=start
  left=%defaultroute
  leftid=54.85.149.143
  right=3.225.20.219
  type=tunnel
  ikelifetime=8h
  keylife=1h
  phase2alg=aes128-sha1;modp1024
  ike=aes128-sha1;modp1024
  keyingtries=%forever
  keyexchange=ike
  leftsubnet=192.168.0.0/16
  rightsubnet=10.10.0.0/16
  dpddelay=10
  dpdtimeout=30
  dpdaction=restart_by_peer
EOF'
cat /etc/ipsec.d/aws.conf

# Run the `add secret command` that you just built
# This is my `add secret command` command, remember to run YOUR instead
sudo bash -c 'cat <<EOF > /etc/ipsec.d/aws.secrets
54.85.149.143 3.225.20.219: PSK "yioHTXdE29JV2HmcDpx8nXhzQwkdR5FW"
EOF'
cat /etc/ipsec.d/aws.secrets

# Apply new config and restart **Network service & IPsec service**
sudo sysctl -p # Apply new sysctl config
sudo chkconfig ipsec on # Ensures IPsec service is enabled on boot.
sudo service network restart
sudo service ipsec restart

# Read IPsec log 
sudo journalctl -u ipsec -f

```


Check if IPsec has started yet


```bash
# Check IPsec and network status
sudo service ipsec status
```


Mine is good now, you can see it shows `Active: active (running)`


```bash
[root@ip-192-168-1-206 ec2-user]# sudo service ipsec status 
Redirecting to /bin/systemctl status ipsec.service
● ipsec.service - Internet Key Exchange (IKE) Protocol Daemon for IPsec
   Loaded: loaded (/usr/lib/systemd/system/ipsec.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2024-08-27 18:16:26 UTC; 35s ago
     Docs: man:ipsec(8)
           man:pluto(8)
           man:ipsec.conf(5)
  Process: 1168 ExecStartPre=/usr/sbin/ipsec --checknflog (code=exited, status=0/SUCCESS)
  Process: 1162 ExecStartPre=/usr/sbin/ipsec --checknss (code=exited, status=0/SUCCESS)
  Process: 628 ExecStartPre=/usr/libexec/ipsec/_stackmanager start (code=exited, status=0/SUCCESS)
  Process: 626 ExecStartPre=/usr/libexec/ipsec/addconn --config /etc/ipsec.conf --checkconfig (code=exited, status=0/SUCCESS)
 Main PID: 1186 (pluto)
   Status: "Startup completed."
   CGroup: /system.slice/ipsec.service
           └─1186 /usr/libexec/ipsec/pluto --leak-detective --config /etc/ipsec.conf --nofork

Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: | setup callback for interface eth0:500 fd 15
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: loading secrets from "/etc/ipsec.secrets"
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: loading secrets from "/etc/ipsec.d/aws.secrets"
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: "Tunnel1" #1: initiating Main Mode
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: "Tunnel1" #1: STATE_MAIN_I2: sent MI2, expecting MR2
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: "Tunnel1" #1: STATE_MAIN_I3: sent MI3, expecting MR3
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: "Tunnel1" #1: Peer ID is ID_IPV4_ADDR: '3.225.20.219'
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: "Tunnel1" #1: STATE_MAIN_I4: ISAKMP SA established {auth=PRESHARED_KEY cipher=aes_128 integ=sha group=MODP1024}
Aug 27 18:16:26 ip-192-168-1-206.ec2.internal pluto[1186]: "Tunnel1" #2: initiating Quick Mode PSK+ENCRYPT+TUNNEL+PFS+UP+IKEV1_ALLOW+IKEV2_ALLOW+SAREF_TRACK+IKE_FRAG_AL...=MODP1024}
Aug 27 18:16:27 ip-192-168-1-206.ec2.internal pluto[1186]: "Tunnel1" #2: STATE_QUICK_I2: sent QI2, IPsec SA established tunnel mode {ESP/NAT=>0xc4f820fd <0x5b2d1f92 xfr...PD=active}
Hint: Some lines were ellipsized, use -l to show in full.
```


