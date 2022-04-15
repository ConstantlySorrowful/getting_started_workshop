---
title : "Labs"
weight : 300
---

# Configuration

Virtual Interfaces
VIO - LEDs, switches
VSI - Streaming data - audio
VSockets - BSD Sockets

Labs
0. Setting up workshop environment
CFN template or KSC
clone workshop repo
describe scripts and cbuild, etc
Build/deploy hello world mqtt - AVH commandline
connect to AWS MQTT test and verify pub/sub messages

1. enable CI/CD
setup github secrets
setup github actions
describe/modify workflow file
add trivial code change and commit/push
watch EC2 instance launch and run simple test
verify workflow run completes successfully in github portal

3. Setup and run Device Advisor
    manually configure DA
    run and watch results in AWS console
    
4. CI/CD for Device Advisor

5. Adding Shadows to DA CI/CD

6. Adding Jobs

7. Adding OTA

8. Backoff Algorithm

9. Device Defender

Interfaces when available in AVH
9. PKCS#11
10. Cellular
11. VSocket
12. VSI - python customization
13. VIO - ?

Labs
0. Setting up workshop environment
  AVH
    Event Engine blueprint
    CFN stack
    ARM AMI image
    clone repos
    install additional software
    Keil Studio Cloud (KSC)
    c9 connect 
    remote connect to device - debug/download?
  Edukit
    Event Engine blueprint
    CFN stack
    clone repos
    connect vscode
    platformio?
    remote connect to device - debug/download?

1. Build/deploy hello world mqtt
  AVH
    KSC
    c9

2. enable CI/CD - mqtt again with github actions
3. 
Setup
Build H/W (to pass DA)
Device Advisor
CI/CD - github
CI/CD - codecommit
SDK APIs
  Shadows
  MQTT
  PKCS#11
  Jobs - Basic
  Jobs - OTA
Rules
Basic Ingest
Basic Jobs
Advanced Jobs/OTA



modules
1. prerequisites
    AWS account
    Github account
    ARM account
    login to KSC
2. getting started
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
3. Directly launch EC2 with AVH AMI
    Find AVH in AWS Marketplace
    select instance type
    add ssh key for local workstation
    launch and copy public IP address
    ssh into EC2 commandline
    remote ssh extension for VSCode
    clone demo repo
    edit code
    build/run from EC2
4. ci/cd workflow
    enable github actions/workflows
    add github secrets
    push minor change to repo
    watch automation workflow
    see results in github
    see EC2 instance start/stop
5. optional - local debug
    KSC - new project for stm32l4 discovery board
    edit source code with cert/key
    connect board usb
    build image
    start debug
6. TBD - Customize VIO - python
7. Jobs
    clone repo
    provision job
    schedule job
8. OTA - local h/w
9. Device Advisor
10. TBD - AVH Debugging
11. PKCS#11
