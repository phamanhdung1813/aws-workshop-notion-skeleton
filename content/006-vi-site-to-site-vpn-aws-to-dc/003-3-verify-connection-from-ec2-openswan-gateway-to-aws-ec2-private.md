+++
title = "3. Verify connection from EC2 Openswan Gateway to AWS - EC2 Private"
weight = 3
+++


Double-check if it’s truly connected to **AWS - EC2 Private’s** Private IPv4.


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/29-588392-image.png)


```bash
ping 10.10.1.141 -c5
```


It’s ok now


```bash
[root@ip-192-168-1-206 ec2-user]# ping 10.10.1.141 -c5
PING 10.10.1.141 (10.10.1.141) 56(84) bytes of data.
64 bytes from 10.10.1.141: icmp_seq=1 ttl=254 time=1.86 ms
64 bytes from 10.10.1.141: icmp_seq=2 ttl=254 time=1.83 ms
64 bytes from 10.10.1.141: icmp_seq=3 ttl=254 time=1.53 ms
64 bytes from 10.10.1.141: icmp_seq=4 ttl=254 time=2.07 ms
64 bytes from 10.10.1.141: icmp_seq=5 ttl=254 time=1.67 ms

--- 10.10.1.141 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4007ms
rtt min/avg/max/mdev = 1.532/1.796/2.079/0.193 ms
```


If we can ping, then Tunnel 1 in the VPN connection details must be Up. If the status is still Down for both tunnels, it’s likely because it takes some time to re-check the connection.


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/29-191786-image.png)


In this workshop, I’ll only use one tunnel, because with my current Static IP VPN connection strategy, it would cause **random asymmetric routing** if I use 2 tunnels in my VPN. You can still use 2 tunnels and avoid this issue by using a Dynamic IP (try it if you’re a curious cat).


