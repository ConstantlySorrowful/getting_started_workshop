---
title : "Lab 1: Launch an EC2 Instance with AVH AMI"
weight : 301
---

**In this lab we will lauch an EC2 instance with the custome AMI prepared by ARM. This AMI is configured with the tools needed to build and test the development of embedded applications using FreeRTOS, CMSIS-Packs, and AWS IoT SDKs. You can then run and debug on emulators for the ARM architecture of your product.**


## In your browser, navigate to **AWS marketplace**
https://aws.amazon.com/marketplace/search/results?searchTerms=arm

1. Search for "arm" and the first item in the results should be for the Arm Virtual Hardware.

![avh_overview](/static/marketplace-1.png)

2. Click the link highlighted in blue and continue to the next page. Here you can read the product overview information and then continue. Then click the "Continue to Subscribe" button.

![avh_overview](/static/marketplace-2.png)

3. Read the terms and conditions and then click the "Continue to Configuration" button.

![avh_overview](/static/marketplace-3.png)

4. Here you can select options, however the defaults should be suitable for this first time. The software version should already show the latest currently available. The pricing information is an estimate for running on a c5.large EC2 instance. We will select a less expensive option in the next step. Click the "Continue to Launch" button.

![avh_overview](/static/marketplace-4.png)

5. On this page there are several selection options. For the Action, Launch from Website is the default. This will be sufficient for this workshop. If you need to adjust other configuration details, select Launch through EC2. Select an EC2 Instance Type of t2.micro. A t2.micro is in the free tier and will be adequate for the workshop labs. 

![avh_overview](/static/marketplace-5.png)

6. Scroll down to select the VPC and subnet settings.  Your default VPC/subnet should already have automatic public IP address assignment enabled, however if you have multiple subnets configured be sure to select one that is enabled for public IP addresses.


![avh_overview](/static/marketplace-6.png)

7. There should be an auto generated security group listed. This will have the access settings we need. Add an ssh key pair that you already have registered in your account or create a new one. Then click "Launch".

![avh_overview](/static/marketplace-7.png)

8. You should now see a page confirming you have successfully launched the EC2 instance with the custom AMI.

![avh_overview](/static/marketplace-8.png)

9. You can now open the AWS Console and see you new EC2 instance starting up.

![avh_overview](/static/marketplace-9.png)

10. Make note of the public IP address shown. You can now open a terminal application and from the command line you can ssh into your instance.

```
[pbutler@darla ~]$ ssh ubuntu@3.82.42.21
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

11. (Optional) I prefer to use VS Code with the Remote SSH Extension to access the EC2 instance. If you already have VS Code installed this option will provide a better experience for editing files in later labs.

