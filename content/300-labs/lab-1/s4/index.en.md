---
title : "Lab 1: Launch an EC2 Instance with AVH AMI (Step 4)"
weight : 4
---


You can now open the AWS Console and see you new EC2 instance starting up.

![avh_overview](/static/marketplace-9.png)

Make note of the public IP address shown. You can now open a terminal application and from the command line you can ssh into your instance.

```
$ ssh ubuntu@xx.xx.xx.xx

The authenticity of host '3.82.42.21 (3.82.42.21)' can't be established.
ECDSA key fingerprint is SHA256:PWQO8CjGeBsSR+nH5ybJ8em/Tk2/UeF/+vUlEP2DEVE.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '3.82.42.21' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 20.04.4 LTS (GNU/Linux 5.13.0-1022-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Thu Jun  9 13:55:07 UTC 2022

  System load:  2.04               Processes:             142
  Usage of /:   51.0% of 23.20GB   Users logged in:       0
  Memory usage: 8%                 IPv4 address for ens5: 172.31.44.13
  Swap usage:   0%

 * Ubuntu Pro delivers the most comprehensive open source security and
   compliance features.

   https://ubuntu.com/aws/pro

0 updates can be applied immediately.


The list of available updates is more than a week old.
To check for new updates run: sudo apt update



+++++++++++++++++++++++++++++++++++++++++++++++++

The Arm Virtual Hardware Beta (Initial) Release is provided free of charge and may be used only for evaluation. By subscribing to access and use the Arm Virtual Hardware Beta Release, you agree to the terms and conditions relevant to free of charge beta licenses in the product End User License Agreement at /home/ubuntu/ArmVirtualHardwareTargets_EULA.pdf

+++++++++++++++++++++++++++++++++++++++++++++++++


Last login: Tue May 10 09:12:11 2022 from 91.168.104.35
==== Arm Virtual Hardware AMI ====
CMSIS packs are installed at /home/ubuntu/packs
ubuntu@ip-172-31-44-13:~$ 
```
