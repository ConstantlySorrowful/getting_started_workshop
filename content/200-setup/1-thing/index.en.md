---
title : "AWS IoT Things"
weight : 1
---

## Setting up Resources in the AWS Console.

We will need a few resources provisioned in AWS. 

### IoT Core - Create a Thing, Certificate, and Policy

Open the AWS Console in your browser and navigate to the IoT Core Service page and then select Manage -> Things from the left column.

- Click Create Things button.
- Select Create a Single Thing and click Next.
- Give your new Thing a name and click Next. (Keep all the defaults for other fields.)
- Select Auto-generate a new certificate (recommended) and click Next.
- Select a policy or create a new one and the click Create thing.
  - [New Policy Examples](https://docs.aws.amazon.com/iot/latest/developerguide/example-iot-policies.html)


**Be sure to download the certicate and private key. You will need then to configure the code.**


![things](/static/create-thing.png)

