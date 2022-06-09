---
title : "Lab 2: AVH in EC2"
weight : 302
---


# Find AVH in AWS Marketplace

# select instance type

# add ssh key for local workstation

# launch and copy public IP address

# ssh into EC2 commandline

# remote ssh extension for VSCode

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
