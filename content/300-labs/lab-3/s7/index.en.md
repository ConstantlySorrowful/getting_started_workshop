---
title : "Lab 3: Building and running code with AVH (Step 7)"
weight : 7
---

## Script to edit credentials files

Then return to the shell in the EC2 instance. We will use a script to apply changes to our certificate and key values and then apply the changes to the include files.


1. Create a helper script in $HOME/bin folder named pem2str. Insert the following contents:

```bash
sed -z 's/\n/\\n/g;s/\\n$/"\n/;s/^/"/' $1 > $1.str
```

Then make it executable:

```bash
chmod +x pem2str
```

2. Now we will use this script to help convert the certificates from **pem** format to C-string format that we can insert into code. Copy the code below and save it to a file (e.g. $HOME/bin/edits.sh). Edit this file and **Replace the values with the correct values for your account**.

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

3. Set this script as excutable.

```bash
chmod +x $HOME/bin/edits.sh
```
4. Be sure your certificate and private key **pem** files are in the $HOME/local folder and then run this script.

```bash
$HOME/bin/edits.sh
```

After running this script, you can confirm the files have been updated:

- $HOME/avh-workshop/amazon-freertos/demos/include/aws_clientcredential.h
- $HOME/avh-workshop/amazon-freertos/demos/include/aws_clientcredential_keys.h

Keep these files for use in a later lab. Either download them to your local computer or upload them to an S3 bucket. If you are using VSCode, you can install the AWS Toolkit extension. The AWS extension will enable easy access to your S3 bucket.

**Reminder: Do NOT commit the credentials files changes back to your github repository. This is a public repo. Anyone can see your private key!**
