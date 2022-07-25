---
title : "Lab 2: Building and running code with AVH (Step 3)"
weight : 3
---

## Fork the examples repository in GitHub

Open a browser and navigate to [AVH_Labs](https://github.com/ConstantlySorrowful/AVH_Labs). In top/right select **Fork**. A copy of this repository needs to be added to your own GitHub account to make changes and configure the CI/CD workflows.

## Clone example code from GitHub

Now we are ready to get started with some example code. In this step we will clone a repository from GitHub. This repository contains a project that implements MQTT Mutual Authentication with FreeRTOS and is configured to use CMSIS-Packs. We will then compile the project using the command line tools from the cmsis-toolbox we installed earlier.


Open a terminal to the EC2 instance and follow these steps.

```
cd $HOME
git clone https://github.com/<your account>/AVH_Labs.git
```
For convienience in this lab we will insert credentials directly into our source code. This is NOT an acceptable practice for actual deployments. In a later lab we will discuss a better practice for handling security credentials in IoT devices. 

You will edit the aws_clientcredential.h and aws_client_credential_keys.h files to add the configuration specific to your AWS account settings. There are some scripts in the repository to help, but first you need to upload the certificate and private key generated when you created a new Thing in your account. The scripts depend on these files being in the $HOME/AVH_Labs/certs directory. If you are using VSCode, you can simple drag/drop the files from your local workstation folder where you have saved them. If you are using a command line shell you can upload the files using scp:

From your local workstation:

```bash
cd /path/to/where/you/saved/the/files
scp <hash>-certificate.pem.crt ubuntu@<ip address of EC2 instance>:AVH_Labs/certs/
scp <hash>-private.pem.key ubuntu@<ip address of EC2 instance>:AVH_Labs/certs/
```

Several settings will be needed that are specific to your AWS Account. Edit the file ./certs/secrets.txt and enter values from your account settings. Do not add spaces after the '='. These values are exported as shell environment variables.

Example:

- AWS_ACCESS_KEY_ID=AKIA3WVBDNxxxxxxxxxx
- AWS_SECRET_ACCESS_KEY=MAgot1dwqPULMo7AWvVH6TRA30cExxxxxxxxxxxx
- AWS_DEFAULT_REGION=us-east-1
- AWS_IAM_PROFILE=armvtRole
- AWS_S3_BUCKET_NAME=myUniqueBucketName
- AWS_SECURITY_GROUP_ID=sg-xxxxxxxx
- AWS_SUBNET_ID=subnet-0d38638917xxxxxxx
- IOT_THING_NAME=armvt
- MQTT_BROKER_ENDPOINT=a2sgxxxxxxxxxx-ats.iot.us-east-1.amazonaws.com

Do not enter values for the following. They will be added automatically by the script below.

- CLIENT_CERTIFICATE_PEM
- CLIENT_PRIVATE_KEY_PEM

See this table for more information:

Secret Name                    | Description
:------------------------------|:--------------------
**AWS Access**                 | Settings and credentials required to acces AWS EC2 and S3 services
`AWS_IAM_PROFILE`              | The [IAM Role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use.html) to be used for AWS access.
`AWS_ACCESS_KEY_ID`          | [Access key pair](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) for the AWS account (as IAM user) that shall be used by the CI workflow for AWS access.
`AWS_SECRET_ACCESS_KEY`      | [Access key pair](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) for the AWS account (as IAM user) that shall be used by the CI workflow for AWS access.
`AWS_S3_BUCKET_NAME`           | The name of the S3 storage bucket to be used for data exchange between GitHub and AWS AMI.
`AWS_DEFAULT_REGION`           | The data center region the AVH AMI will be run on. For example `eu-west-1`.
`AWS_SECURITY_GROUP_ID`        | The id of the [VPC security group](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) to add the EC2 instance to. Shall have format `sg-xxxxxxxx`.
`AWS_SUBNET_ID`                | The id of the [VPC subnet](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html#view-subnet) to connect the EC2 instance to. Shall have format `subnet-xxxxxxxx`.
**IoT Cloud Access**           | Settings and credentials required to connect an [AWS IoT Thing](https://github.com/MDK-Packs/Documentation/tree/master/AWS_Thing)
`CLIENT_CERTIFICATE_PEM`       | Cut/Paste from ./certs/secrets.txt as a single long string. Be sure to remove double-quotes.
`CLIENT_PRIVATE_KEY_PEM`       | Cut/Paste from ./certs/secrets.txt as a single long string. Be sure to remove double-quotes.
`IOT_THING_NAME`               | AWS IoT Core Thing name.
`MQTT_BROKER_ENDPOINT`         | MQTT broker Endpoint from AWS Console IoT Core Settings page.

Then return to the shell in the EC2 instance. A script is provided that will append secrets.txt with the certificate and key values and then apply the changes to the include files.

```bash
cd $HOME/AVH_Labs/certs
./edit-creds.sh
```

After running the edit-creds.sh script, you can confirm the files have been updated:

- $HOME/AVH_Labs/amazon-freertos/demos/include/aws_clientcredential.h
- $HOME/AVH_Labs/amazon-freertos/demos/include/aws_clientcredential_keys.h

Keep these files and ./certs/secrets.txt for use in a later lab. Either download them to your local computer or upload them to an S3 bucket. If you are using VSCode, you can install the AWS Toolkit extension. The AWS extension will enable easy access to your S3 bucket.

**Reminder: Do NOT commit the credentials files changes back to your github repository. This is a public repo. Anyone can see your private key!**
