---
title : "Lab 1: Launch an EC2 Instance with AVH AMI (Step 3)"
weight : 13
---

On this page there are several selection options. For the Action, Launch from Website is the default. This will be sufficient for this workshop. If you need to adjust other configuration details, select Launch through EC2. Select an **EC2 Instance Type** of t3.large. This will be adequate for the workshop labs.

![avh_overview](/static/marketplace-5.png)

Scroll down to select the VPC and subnet settings.  Your default VPC/subnet should already have automatic public IP address assignment enabled, however if you have multiple subnets configured be sure to select one that is enabled for public IP addresses.


![avh_overview](/static/marketplace-6.png)

There should be an auto generated security group listed. This will have the access settings we need. Add an ssh key pair that you already have registered in your account or create a new one. Then click "Launch".

![avh_overview](/static/marketplace-7.png)

You should now see a page confirming you have successfully launched the EC2 instance with the custom AMI.

![avh_overview](/static/marketplace-8.png)

