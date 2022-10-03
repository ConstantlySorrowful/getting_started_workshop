---
title : "Lab 7: Working With STM32U5 in Keil Studio Cloud (KSC) (Step 1)"
weight : 1
---

Open [Keil Studio Cloud](https://studio.keil.arm.com) 

If you do not already have an Arm account you can quickly create one by clicking the Sign up link.

![arm signup](/static/ksc-login.png)

When you open Keil Studio Cloud for the first time you will need to enable access to your GitHub account.

1. Click the person icon in the lower left and select **Show User Profile**
2. Then click **Connect to GitHub**

![github profile 0](/static/github-profile-0.png)

3. Enter your GitHub credentials to complete the connection.

![github profile 2](/static/github-profile-2.png)

4. Now you can go to **File - Clone...** to clone your repository

![clone project](/static/clone.png)

![Import project dialog](/static/import_project2.png)

**Recommended to fork this repository into your own GitHub account**

https://www.github.com/constantlysorrowful/aws_mqtt_mutualauth_demo.git

A project name will be auto generated. Then click Add Project.

# Setup AWS Toolkit

1. Enable the AWS Toolkit in the IDE by selecting the **Extensions** icon on the left and click the slider to on. You will then see the AWS icon appear on the left column.

![aws tk 0](/static/aws-tk-0.png)

2. Edit credentials profile by selecting **more items eliplsis** and then **Choose AWS Profile**. Then select **Edit Credentials**.

![aws tk 3](/static/aws-tk-3.png)
![aws tk 2](/static/aws-tk-2.png)

3. Change the **aws_access_key_id** and **aws_secret_access_key** values to match.
![aws tk 4](/static/aws-tk-4.png)

4. Confirm the region is set to **US West (N. California)**. If needed you can right click on the current region and select **Show or Hide Regions** and then from the dropdown list select **us-west-1**.
![aws tk 1](/static/aws-tk-1.png)