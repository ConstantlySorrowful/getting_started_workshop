---
title : "AWS IoT Things"
weight : 1
---

## Setting up Resources in the AWS Console.

We will need a few resources provisioned in AWS. 

### IoT Core - Create a Thing, Certificate, and Policy

Open the AWS Console in your browser and navigate to the IoT Core service page. 

- Select Create Thing.
- Select Create a Single Thing and click Next.
- Give your new Thing a name and click Next. (Keep all the defaults for other fields.)
- Select Auto-generate a new certificate (recommended)
- Select a policy or create a new one.

**Be sure to download the certicate and private key. We will need then to configure the code.**

![things](/static/create-thing.png)

