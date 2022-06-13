---
title : "Lab 2: Building and running code with Arm Virtual Hardware (Step 5)"
weight : 5
---

## Build and run the code

Now that you have completed:

- Creating a Thing in AWS Console
- Creating a policy and certificate
- uploading the certificate and private key to the EC2 instance
- edited the credentials configuration files

You can now build the project using the cmsis-toolbox utility 'cbuild'.

```
cd $HOME/AVH_Demo
cbuild demo.VHT_MPS3_Corstone_SSE-300.cprj
```
You should see many lines of compiling scroll past, but at the end you should see:

```
info cbuild: build finished successfully!
```

