---
title : "Summary"
weight : 400
---

Follow these steps!

Labs

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
    
Labs

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
