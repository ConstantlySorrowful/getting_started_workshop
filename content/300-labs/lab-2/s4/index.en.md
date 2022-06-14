---
title : "Lab 2: Building and running code with Arm Virtual Hardware (Step 4)"
weight : 4
---

## Clone example code from GitHub

Now we are ready to get started with some example code. In this step we will clone a repository from GitHub. This repository contains a project that implements MQTT Mutual Authentication with FreeRTOS and is configured to use CMSIS-Packs. We will then compile the project using the command line tools from the cmsis-toolbox we installed earlier.


Open a terminal to the EC2 instance and follow these steps.

```
cd $HOME
git clone https://github.com/ConstantlySorrowful/AVH_Labs.git
```
We now need to edit the aws_clientcredential.h and aws_client_credential_keys.h files to add the configuration specific to your AWS account settings. There are some scripts in the repository to help, but first we need to upload the certificate and private key generated when you created a new Thing in your account. The scripts depend on these files being the $HOME/AVH_Labs/certs directory. If you are using VSCode, you can simple drag/drop the files from your local workstation folder where you have saved them. If you are using a command line shell you will need to use scp:

From your local workstation:

```
cd /path/to/where/you/saved/the/files
scp <hash>-certificate.pem.crt ubuntu@<ip address of EC2 instance>:certs/
scp <hash>-private.pem.key ubuntu@<ip address of EC2 instance>:certs/
```

Several settings will be needed that are specific to your AWS Account. Edit the file ./certs/secrets.txt and enter values from you account settings.

- AWS_ACCESS_KEY_ID = 
- AWS_SECRET_ACCESS_KEY = 
- AWS_DEFAULT_REGION = 
- AWS_IAM_PROFILE = 
- AWS_S3_BUCKET_NAME = 
- AWS_SECURITY_GROUP_ID = 
- AWS_SUBNET_ID = 
- IOT_THING_NAME = 
- MQTT_BROKER_ENDPOINT = 

Then return to the shell in the EC2 instance. A script is provided that will append secrets.txt with the certificate and key values and then apply the changes to the include files.

```
cd $HOME/AVH_Labs/certs
./scripts/edit-creds.sh
```

After running the edit-creds.sh script, you can confirm the files have been updated:

- $HOME/AVH_Labs/amazon-freertos/demos/include/aws_clientcredential.h
- $HOME/AVH_Labs/amazon-freertos/demos/include/aws_clientcredential_keys.h

Keep the files produced in $HOME/certs. You will need them again later.
