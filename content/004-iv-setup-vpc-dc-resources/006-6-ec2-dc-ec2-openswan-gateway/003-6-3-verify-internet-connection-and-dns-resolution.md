+++
title = "6.3 Verify internet connection and DNS resolution"
weight = 3
+++


Try to ping AWS


```bash
ping amazon.com -c5
```


It’s all good


```bash
[ec2-user@ip-192-168-1-206 ~]$ ping amazon.com -c5
PING amazon.com (54.239.28.85) 56(84) bytes of data.
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=1 ttl=250 time=1.25 ms
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=2 ttl=250 time=0.667 ms
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=3 ttl=250 time=0.974 ms
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=4 ttl=250 time=0.976 ms
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=5 ttl=250 time=1.34 ms

--- amazon.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4017ms
rtt min/avg/max/mdev = 0.667/1.043/1.340/0.238 ms
```


In case your ping fails, try the command below and ping again.


```bash
# This should resolve the DNS problem
sudo sh -c "echo nameserver 1.1.1.1 > /etc/resolv.conf"
```


