+++
title = "4. Test SSH from DC - EC2 Openswan Gateway to AWS - EC2 Private"
weight = 4
+++


First, we edit the Security Group - **AWS - Private** to allow SSH from **DC - EC2 Openswan Gateway**.


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/30-970092-image.png)


Fill in the IPv4 Private address of **DC - EC2 Openswan Gateway** with a subnet mask of /32.


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/30-433482-image.png)


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/30-879347-image.png)


Now we’re allowed to SSH into **AWS - Private** if the connecting IP matches.


If you’re wondering why it’s an **IPv4 Private** address, it’s because the VPN connection is already set up. The two servers now think they’re on the same network, they no longer consider themselves connected through the internet, so they use IPv4 Private addresses to connect.


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/30-810444-image.png)


If we want SSH to be possible, we will need to transfer the **AWS - EC2 Private** key (`aws-ec2-private.pem`) from our local machine to **DC - EC2 Openswan Gateway**.


```bash
# Modify keypair permission (required by AWS)
Format:
chmod 400 <path to the aws-ec2-private.pem key>

Example - my filled command:
chmod 400 Downloads/aws-ec2-private.pem


# Copy the key from local machine to DC - EC2 Openswan Gateway
Format:
scp -i <path to the dc-ec2-openswan-gateway.pem key> <path to the aws-ec2-private.pem key> ec2-user@<Public IPv4> 

Example - my filled command:
scp -i Downloads/dc-ec2-openswan-gateway.pem Downloads/aws-ec2-private.pem ec2-user@54.85.149.143:/home/ec2-user/ 
```


It looks like this if your copy is successful.


```bash
 ~  scp -i Downloads/dc-ec2-openswan-gateway.pem Downloads/aws-ec2-private.pem ec2-user@54.85.149.143:/home/ec2-user/                               INT ✘ │ 3.3.0  │ 01:40:24 AM 
aws-ec2-private.pem     100% 1678     6.4KB/s   00:00    
```


SSH again into **DC - EC2 Openswan Gateway** (use your previous command, I won’t rewrite the instructions here).


Type `ls` to show all files. You should see the key to SSH into **AWS - EC2 Private** there.


```bash
[ec2-user@ip-192-168-1-206 ~]$ ls
aws-ec2-private.pem
```


Run the SSH command now


```bash
# Modify keypair permission (required by AWS)
Format:
ssh -i aws-ec2-private.pem ec2-user@<AWS - EC2 Private - Private IPv4>

Example - my filled command:
ssh -i aws-ec2-private.pem ec2-user@10.10.1.141
```


I can SSH into **DC - EC2 Openswan Gateway** from my local computer now.


```bash
[ec2-user@ip-192-168-1-206 ~]$ ssh -i aws-ec2-private.pem ec2-user@10.10.1.141
Last login: Tue Aug 27 18:52:11 2024 from 192.168.1.206
   ,     #_
   ~\_  ####_        Amazon Linux 2
  ~~  \_#####\
  ~~     \###|       AL2 End of Life is 2025-06-30.
  ~~       \#/ ___
   ~~       V~' '->
    ~~~         /    A newer version of Amazon Linux is available!
      ~~._.   _/
         _/ _/       Amazon Linux 2023, GA and supported until 2028-03-15.
       _/m/'           https://aws.amazon.com/linux/amazon-linux-2023/

[ec2-user@ip-10-10-1-141 ~]$ who
ec2-user pts/0        2024-08-27 19:00 (192.168.1.206)
```


