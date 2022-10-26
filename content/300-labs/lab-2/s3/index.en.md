---
title : "Lab 2: Launch an EC2 Instance with AVH AMI (Step 3)"
weight : 3
---

On this page there are several selection options. For the Action, **Launch from Website** is the default. This will be sufficient for this workshop. If you need to adjust other configuration details, select Launch through EC2. Select an **EC2 Instance Type** of c5.large. This will be adequate for the workshop labs.

![avh_overview](/static/marketplace-5.png)

Scroll down to select the VPC and subnet settings.  Your default VPC/subnet should already have automatic public IP address assignment enabled, however if you have multiple subnets configured be sure to select one that is enabled for public IP addresses. [See VPC public IP addresses](/300-labs/lab-1/s3/publicip)

**Also, not all instance region/type/subnet combinations are supported.**

**Recommended: us-east-1, c5large, any subnet except 'e' should be ok.**

**Subnet 'e' in us-east-1 is not supported.** 

**Reminder: Be sure to provision resources (e.g. EC2 Instance, S3 Bucket, etc.) in the same region.**

![avh_overview](/static/marketplace-6.png)

There should be an auto generated security group listed. This will have the access settings we need. 

Add an ssh key pair that you already have registered in your account or create a new one. Then click **Launch**.

![avh_overview](/static/marketplace-7.png)

If a default security group is not available, select the **Create New Based on Seller Settings** button. A new page will provide options for name and description. The only port needed for access is for SSH. Then click **Save**. After returning to the previous page click **Launch**.

![avh_mkt-10](/static/marketplace-10.png)

You should now see a page confirming you have successfully launched the EC2 instance with the custom AMI.

![avh_overview](/static/marketplace-8.png)

