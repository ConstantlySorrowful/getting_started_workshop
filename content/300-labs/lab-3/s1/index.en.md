---
title : "Lab 3: Automate with GitHub Actions CI/CD Workflows (Step 1)"
weight : 1
---


## GetHub Secrets - Values 

The following (secret) configuration values need to be added to the repositories. 

1. In your browser, navigate to the GitHub repository you have forked. 
2. Select the Setting gear icon and then scroll down in the left column to find **Secrets/Actions**. 
3. Then for each new value click **New repository secret**.

![github 1](/static/github-secrets-1.png)


Here you will enter the values we saved earlier in ./certs/secrets.txt. 

Add a name/value pair for each item. Do not add quotes to the values entered. The script used earlier (edit-creds.sh) added quotes to the generated values for **CLIENT_CERTIFICATE_PEM** and **CLIENT_PRIVATE_KEY**. Please remove them when entering them as a GitHub Secret.

![github 2](/static/github-secrets-2.png)


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
