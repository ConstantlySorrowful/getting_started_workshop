---
title : "Setup"
weight : 200
---

# Initial Keil Studio Cloud Setup
- Create/Sign In to KSC
- Enable Github access
- Enable AWS Toolkit

For this workshop, you need an **Arm account** (or use an existing [Mbed Account](https://os.mbed.com/account/signup)). [Sign up](https://developer.arm.com/register?returnUrl=/) to get access to:
- [Keil Studio](https://studio.keil.arm.com) (for cloud development)
- Free [MDK-Community](https://keil.arm.com/mdk-community) edition (for desktop development)


# Github Account Setup
- Github Actions
- Github Secrets

# Common Setup Steps

For each of the labs in the next section of the workshop, there is a common set of steps that will repeat.

- Fork a repoistory from Github into your own account
- Import the project into KSC
- Edit configuration code to use your AWS endpoint, thing name, certificate, key, etc.
- 

https://arm-software.github.io/AVH/main/infrastructure/html/run_ami_github.html#GitHub_hosted

**Amazon Web Service (AWS) account** with:
- Amazon EC2 (elastic cloud) access
- Amazon S3 (storage) access
- Registration to access AVH Amazon Machine Image [AVH AMI](https://aws.amazon.com/marketplace/search/results?searchTerms=Arm+Virtual+Hardware)
- User role setup for scripted API access


https://github.com/ARM-software/AVH-AWS_MQTT_Demo.git

- Fork this repository with at least _Write_ access rights
- Store the AWS account configuration (obtained in step 1) as
    [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets) - ***AWS Access** values in the forked repository

