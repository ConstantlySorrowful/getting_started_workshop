---
title : "Setup"
weight : 200
---

# Setup AWS and Github Resources

Before we can jump into the labs we need to provision resources in the AWS Console. Be sure to provision resources in the same region. It is recommended to use "us-east-1". Most testing for this workshop was in "us-east-1". Other regions may be ok, but not confirmed by testing.

Resources create in IAM are global (e.g. Users, Roles, Policies) and may be used in any region.

The following resources need to be provisioned in the same region.

**EC2 Instance**

EC2 allows users to launch and manage multiple virtual machines (instances). Choose a size that fits your requirements. General purpose, compute optimized, memory optimized, storage/network throughput/latency optimized, etc. See the details [here](https://aws.amazon.com/ec2/). The AWS platform provides preconfigured templates — known as AMIs (Amazon Machine Images). This workshop will use a custom AMI prepared by Arm specifically for Arm Virtual Hardware.

**Thing / Certificate / IoT Policy**

IoT **Things** are devices connected to AWS IoT Core network. Security for each device is provided by unique certificates and policies defining the allowed access to resources by that device.

**S3 Bucket**

Simple Storage Service. Amazon S3 is an object storage service that offers industry-leading scalability, data availability, security, and performance. This workshop will use an S3 bucket for saving artifacts from the build and test phases.

