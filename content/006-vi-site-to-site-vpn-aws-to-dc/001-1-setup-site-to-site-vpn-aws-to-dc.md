+++
title = "1. Setup Site-to-Site VPN - AWS to DC"
weight = 1
+++


Fill out the form as follows, with explanations:

1. **Static IP Prefixes:** You will need to fill in two CIDRs. The first is our **VPC - DC (192.168.0.0/16)**, and the second is **VPC - AWS (10.10.0.0/16)**.
2. **Local IPv4 Network CIDR:** Fill in our **VPC - DC** CIDR **(192.168.0.0/16)**.
3. **Remote IPv4 Network CIDR:** Fill in our **VPC - AWS** CIDR **(10.10.0.0/16)**.

![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/27-778339-image.png)


That’s everything, click "Create" You should see the new VPN connection from **AWS to DC**. We will move on to the next step while waiting for this VPN to be ready.


![image.png](/images/006-vi-site-to-site-vpn-aws-to-dc/27-129251-image.png)


