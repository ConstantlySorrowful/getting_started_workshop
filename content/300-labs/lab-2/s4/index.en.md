---
title : "Lab 2: Building and running code with Arm Virtual Hardware (Step 4)"
weight : 4
---

## Clone example code from GitHub

Now we are ready to get started with some example code. In this step we will clone a repository from GitHub. This repository contains a project that implements MQTT Mutual Authentication with FreeRTOS and is configured to use CMSIS-Packs. We will then compile the project using the command line tools from the cmsis-toolbox we installed earlier.


Open a terminal to the EC2 instance and follow these steps.

```
cd $HOME
git clone https://github.com/butlerpaul/AVH_Demo.git
```
We now need to edit the aws_clientcredential.h and aws_client_credential_keys.h files to add the configuration specific to your AWS account settings. There are some scripts in the repository to help, but first we need to upload the certificate and private key generated when you created a new Thing in your account. The scripts depend on these files being the $HOME/certs directory. If you are using VSCode, you can simple drag/drop the files from your local workstation folder where you have saved them. If you are using a command line shell you will need to use scp:

First, in the EC2 instance shell:

```
mkdir -p $HOME/certs
```

Then, from your local workstation:

```
cd /path/to/where/you/saved/the/files
scp <hash>-certificate.pem.crt ubuntu@<ip address of EC2 instance>:certs/
scp <hash>-private.pem.key ubuntu@<ip address of EC2 instance>:certs/
```

Several settings will be needed that are specific to your AWS Account. Edit the file ./config_files.secrets.txt and enter values from you account settings. However, leave the certificate and key values empty for now. A script is provided that will format them as needed for our use.

AWS_ACCESS_KEY_ID = 
AWS_SECRET_ACCESS_KEY = 
AWS_DEFAULT_REGION = 
AWS_IAM_PROFILE = 
AWS_S3_BUCKET_NAME = 
AWS_SECURITY_GROUP_ID = 
AWS_SUBNET_ID = 
IOT_THING_NAME = 
MQTT_BROKER_ENDPOINT = 
CLIENT_CERTIFICATE_PEM = 
CLIENT_PRIVATE_KEY_PEM = 


Then back to the shell in the EC2 instance:

```
cd $HOME/AVH_Demo
./scripts/gen-creds.sh
```

This helper script generates another file in $HOME/certs named config-creds.sh

This file will still require editing to add your AWS IoT Endpoint and ThingName. Open the file with an editor and replace **"Endpoint"** with the value from the AWS Console - IoT Core service Settings page. And replace **"ThingName"** with the name you gave it during Thing creation earlier.

```
export MQTT_BROKER_ENDPOINT=<Endpoint>-ats.iot.us-east-1.amazonaws.com
export IOT_THING_NAME=<ThingName>
```

Then run another helper script to complete the configuration:

```
cd $HOME/AVH_Demo
./scripts/edit-creds.sh
```

If this completes without errors, you can confirm the files:

$HOME/AVH_Demo/amazon-freertos/demos/include/aws_clientcredential.h and aws_clientcredential_keys.h now have the modifications needed before compiling the code.

Keep the files in $HOME/certs. You will need them again later.
