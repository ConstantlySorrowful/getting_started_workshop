---
title : "Lab 3: Building and running code with AVH (Step 6)"
weight : 6
---

## Collect settings

Several settings will be needed that are specific to your AWS Account. To help with setup in your AWS account we will use a **Cloud Formation** template to create some required resources in your account.

1. First clone this repository into your local PC:
**https://github.com/ARM-software/AVH-GetStarted.git**

```bash
cd $HOME
git clone https://github.com/ARM-software/AVH-GetStarted.git
cd AVH-GetStarted/infrastructure/cloudformation
```
2. Open the file **Arm-AVH-CloudFormation-Template.yaml** in an editor. Scroll down until you find (approx. line 92)

```yaml
   - repo:YOUR_GITHUB_ORG/YOUR_GITHUB_REPO:*
```

3. Replace **YOUR_GITHUB_ORG** with your actual github account name.
4. Replace **YOUR_GITHUB_REPO** with the name of your cloned repo. (e.g. **AWS_MQTT_MutualAuth_Demo**)
5. There are also 2 lines that need to be deleted. Each line will begine with **PermissionBoundary**. (approx. lines 75 and 108). Be sure to save your changes to the file.

5. Navigate to **Cloud Formation** in you AWS Console and select the dropdown list **Create stack**. And then choose **With new resources (standard)**.

![create stack1](/static/create-stack-1.png)

6. Select **Upload a template file**. Then press the **Choose file** button and find your local copy of the template file. Then select **Next**.

![create stack2](/static/create-stack-2.png)

7. Provide a name for your new stack and a unique name for a new S3 bucket. Then select the dropdown list and choose a VPC ID. (default). Then click **Next**.

![create stack3](/static/create-stack-3.png)

8. You can click through **Next** again until final page. The default valuse for these setting will be sufficient.

9. On the last page check the **Acknowledge** setting and then click **Submit**.

![create stack4](/static/create-stack-4.png)

Stack create will take several minutes. You will initially see **CREATE IN PROGRESS**

![create stack5](/static/create-stack-5.png)

You should see a **CREATE COMPLETE** when ready to continue.

![create stack6](/static/create-stack-6.png)


10. Create a new file in your EC2 instance **$HOME** folder. Name it ./secrets.txt and enter values from your account settings.

Some of these values you can find after creating the new stack in **Output** tab.

![create stack7](/static/create-stack-7.png)

Example:

```bash
AWS_ASSUME_ROLE = arn:aws:iam::xxxxxxxxxxxx:role/Proj-AVHRole
AWS_DEFAULT_REGION=us-east-1
AWS_IAM_PROFILE = Proj-AVHInstanceRole
AWS_S3_BUCKET_NAME = avh-unique-bucket-name
AWS_SECURITY_GROUP_ID = sg-0f2c06d51de5c8732
AWS_SUBNET_ID = subnet-xxxxxxx
IOT_THING_NAME = myThingName
MQTT_BROKER_ENDPOINT = a2sgxxxxxxxxxx-ats.iot.us-east-1.amazonaws.com
```

Edit each of these values to be correct for you account.

**MQTT_BROKER_ENDPOINT** can be found in the IoT Core service page:

![settings 0](/static/settings-0.png)
![settings 1](/static/settings-1.png)


**AWS_SUBNET_ID** can be found on your EC2 instance page. Select the **Security** tabs to locate the settings values needed.

![settings 2](/static/settings-2.png)

11. Create a helper script in $HOME/bin folder named pem2str. Insert the following contents:

```bash
sed 's/^/"/;s/$/\\n" \\/' $1 > $1.str
```

Then make it executable:

```bash
chmod +x pem2str
```

12. Now we will use this script to help convert the certificates from **pem** format to C-string format that we can insert into code. Execute this scripts below to apply the changes to our code. **Replace the values with the correct values for your account**.

```
cd $HOME/local/
$HOME/bin/pem2str <hash>-certificate.pem.crt
$HOME/bin/pem2str <hash>-private.pem.key 
export CLIENT_CERTIFICATE_PEM=`cat <hash>-certificate.pem.crt.str`
export CLIENT_PRIVATE_KEY_PEM=`cat <hash>-private.pem.key.str`
export MQTT_BROKER_ENDPOINT=xxxxxxxxxxxxx-ats.iot.us-east-1.amazonaws.com
export IOT_THING_NAME=xxxxx
cd $HOME/AWS_MQTT_MutualAuth_Demo/amazon-freertos/demos/include/
envsubst <aws_clientcredential_keys.h.in >aws_clientcredential_keys.h
envsubst <aws_clientcredential.h.in >aws_clientcredential.h
```

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
