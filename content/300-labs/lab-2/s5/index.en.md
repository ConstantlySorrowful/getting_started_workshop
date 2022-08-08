---
title : "Lab 2: Building and running code with AVH (Step 5)"
weight : 5
---

## Upload credentials

For convienience in this lab we will insert credentials directly into our source code. This is NOT an acceptable practice for actual deployments. In a later lab we will discuss a better practice for handling security credentials in IoT devices. 

You will edit the **aws_client_credential.h** and **aws_client_credential_keys.h** files to add the configuration specific to your AWS account settings. There are some scripts in the repository to help, but first you need to upload the certificate and private key generated when you created a new Thing in your account. The scripts depend on these files being in the **$HOME/avh-workshop/certs** directory. If you are using VSCode with the Remote SSH extension you can use the drag/drop feature to upload files to the EC2 instance. If you are using a command line shell you can upload the files using scp:

From your local workstation:

```bash
cd /path/to/where/you/saved/the/files
scp <hash>-certificate.pem.crt ubuntu@<ip address of EC2 instance>:avh-workshop/certs/
scp <hash>-private.pem.key ubuntu@<ip address of EC2 instance>:avh-workshop/certs/
```
