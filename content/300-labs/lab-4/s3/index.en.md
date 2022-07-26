---
title : "Lab 4: Moving your project to Keil Studio Cloud (KSC) (Step 3)"
weight : 3
---

## Edit configuration files

In ./mqtt_pub_sub/config_files/:

- **demo_config.h**

- **aws_clientcredential_keys.h**

In an earlier lab you edited these files by running a script. You should have saved these files either on your local workstation or your S3 bucket. If you did not, they should still be available in your EC2 instance.

Upload the saved credentials files into ./mqtt_pub_sub/config_files/. KSC supports Drag/Drop from your local PC or you can also use the AWS Toolkit extension to retrieve them from your S3 bucket.

**Reminder: Do NOT commit the credentials files changes back to your github repository! This is a public repo. Anyone can see your private key!**
