---
title : "Lab 3: Building and running code with AVH (Step 6)"
weight : 6
---

## Collect settings

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

**AWS_ACCESS_KEY_ID** and **AWS_SECRET_ACCESS_KEY** will come from the AWS Console - IAM service page.
The secret key is only visible at the time you create it. Create a new set if you have not yet created any or did not save them earlier.

See [Manging access keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_CreateAccessKey) for more details.

Each of the following were created in the **Setup** section of the workshop.

- **AWS_IAM_PROFILE** is the **Role** you created earlier.
- **AWS_S3_BUCKET_NAME**
- **IOT_THING_NAME**

**MQTT_BROKER_ENDPOINT** can be found in the IoT Core service page:

![settings 0](/static/settings-0.png)
![settings 1](/static/settings-1.png)



**AWS_SECURITY_GROUP_ID** and **AWS_SUBNET_ID** can be found on your EC2 instance page. Select the **Security** tabs to locate the settings values needed.

![settings 2](/static/settings-2.png)

Do not enter values for the following. They will be added automatically by the script below.

- **CLIENT_CERTIFICATE_PEM**
- **CLIENT_PRIVATE_KEY_PEM**

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
