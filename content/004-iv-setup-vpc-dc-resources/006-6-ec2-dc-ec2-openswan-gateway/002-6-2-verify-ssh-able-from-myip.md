+++
title = "6.2 Verify SSH-able from MyIP"
weight = 2
+++


Let’s go to the Instance Details, you can see that DC - EC2 Openswan Gateway is already up with a Public IPv4 address.


![image.png](/images/004-iv-setup-vpc-dc-resources/006-6-ec2-dc-ec2-openswan-gateway/21-216889-image.png)


Open your terminal and connect via SSH to the **DC - EC2 Openswan Gateway** using the `dc-ec2-openswan-gateway.pem` file we already downloaded.


Note: Lines preceded by ‘#’ are comments, so you don’t have to run those commands in the terminal.


```bash
# Modify keypair permission (required by AWS)
Format:
chmod 400 <path to the dc-ec2-openswan-gateway.pem key>

Example - my filled command:
chmod 400 Downloads/dc-ec2-openswan-gateway.pem


# Start SSH
Format:
ssh -i <path to the dc-ec2-openswan-gateway.pem key> ec2-user@<Public IPv4>

Example - my filled command:
ssh -i Downloads/dc-ec2-openswan-gateway.pem ec2-user@54.85.149.143
```


I can SSH into the **DC - EC2 Openswan Gateway** from my local computer now.


```bash
 ~  ssh -i Downloads/dc-ec2-openswan-gateway.pem ec2-user@54.85.149.143                                                                                 ✔ │ 3.3.0  │ 12:14:37 AM 
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

[ec2-user@ip-192-168-1-206 ~]$ whoami
ec2-user

```


