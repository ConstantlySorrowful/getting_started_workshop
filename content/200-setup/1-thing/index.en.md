---
title : "AWS IoT Things"
weight : 1
---

## Setting up Resources in the AWS Console.

We will need a few resources provisioned in AWS. 

### IoT Core - Create a Thing, Certificate, and Policy

**1.** Open the AWS Console in your browser and navigate to the IoT Core Service page and then select **Manage -> Things** from the left column.

![create thing 1](/static/iot-core-create-thing-1.png)

**2.** Click Create Things button.

![create thing 2](/static/iot-core-create-thing-2.png)

**3.** Select Create a Single Thing and click Next.

![create thing 3](/static/iot-core-create-thing-3.png)

**4.** Give your new Thing a name and click Next. (Keep all the defaults for other fields.)

![create thing 4](/static/iot-core-create-thing-4.png)

**5.** Select Auto-generate a new certificate (recommended) and click Next.

![create thing 5](/static/iot-core-create-thing-5.png)

**6.** If you alread have a policy defined select the checkbox on the left or create a new one and then click Create thing.

![create thing 6](/static/iot-core-create-thing-6.png)

**7.** If you selected creating a new policy a new tab will open in your browser. Keep the **Attach policies to certificate** tab open. We will return to it to complete creating the thing after defining a policy. Give your policy a name and select the **JSON** button on the right. Then edit the policy document. You can copy and insert the example JSON code below.Then click **Create** at the bottom.

See [New Policy Examples](https://docs.aws.amazon.com/iot/latest/developerguide/example-iot-policies.html) for more details about policies.

![create thing 7](/static/iot-core-create-thing-7.png)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "iot:*",
        "logs:*"
      ],
      "Resource": [
        "*"
      ]
    }
  ]
}
```
After creating the new policy return to the **Attach policies to certificate** tab in your browser and select the checkbox for the new policy in the list. Then click **Create thing**.

![create thing 6](/static/iot-core-create-thing-6.png)

**8.** Now you must download the device certificate, public key, and private key. Save them on your local PC for later use. Then click **Done**.

![create thing 8](/static/iot-core-create-thing-8.png)
