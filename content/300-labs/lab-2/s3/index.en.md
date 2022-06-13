---
title : "Lab 2: Building and running code with Arm Virtual Hardware (Step 3)"
weight : 3
---

In this lab we will use the EC2 instance we launched in the prior lab to clone a repository from GitHub. We will then compile the project for a Corestone-300 architecture. And finally run the application using the Arm Virtual Hardware emulator for the Corstone-300.

with the custome AMI prepared by ARM. This AMI is configured with the tools needed to build and test the development of embedded applications using FreeRTOS, CMSIS-Packs, and AWS IoT SDKs. You can then run and debug on emulators for the ARM architecture of your product.


# install cmsis-toolbox latest

# clone demo repo

# edit code

# build/run from EC2





- Select Fork repository into your own github account
- Login to Keil Studio and import your first project
- Use AWS Toolkit to create a thing, certificate, policy
- Save cert and key in KSC file
- Edit code to use new credentials
- Build it!
- connect to AWS MQTT test and subscribe to view MQTT messages from you virtual device
- Run your project in the AVH simulation and verify pub/sub messages

    KSC - import/clone mqtt demo
    use AWS Toolkit
        create a thing
        generate a cert
        create and attach a policy
        save certs
        edit code to include cert/key
    build/run
    AWS console subscribe
    see pub/sub messages
