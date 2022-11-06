---
title : "Lab 3: Building and running code with AVH (Step 7)"
weight : 7
---

## Script to edit credentials files

Then return to the shell in the EC2 instance. A script is provided that will append secrets.txt with the certificate and key values and then apply the changes to the include files.

```bash
cd $HOME/avh-workshop/certs
./edit-creds.sh
```

After running the edit-creds.sh script, you can confirm the files have been updated:

- $HOME/avh-workshop/amazon-freertos/demos/include/aws_clientcredential.h
- $HOME/avh-workshop/amazon-freertos/demos/include/aws_clientcredential_keys.h

Keep these files and ./certs/secrets.txt for use in a later lab. Either download them to your local computer or upload them to an S3 bucket. If you are using VSCode, you can install the AWS Toolkit extension. The AWS extension will enable easy access to your S3 bucket.

**Reminder: Do NOT commit the credentials files changes back to your github repository. This is a public repo. Anyone can see your private key!**
