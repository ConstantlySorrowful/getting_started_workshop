---
title : "Lab 2: VPC Public IP Addresses"
toc: false
weight : 3
---

Your default subnet should already have **Auto-assign IP settings** enabled. However, if you have selected a different subnet for launching the EC2 instance, please confirm this setting is enabled. You will need a public IP address to access your EC2 instance.

1. Open the AWS Console in your browser and navigate to the VPC service page. 
2. Along the left column, select **Subnets**

![public 1](/static/publicip-1.png)

3. Select the checkbox next to the subnet you wish to edit.
4. And then select the dropdown list for **Actions** and choose **Edit subnet settings**

![public 3](/static/publicip-3.png)

5. Enable the setting **Auto-assign IP settings**

![public 4](/static/publicip-4.png)
