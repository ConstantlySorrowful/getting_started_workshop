---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Step 3)"
weight : 3
---

## Create a new certificate and attach a policy

1. Click the **AWS** icon on the left side of the IDE window to open the **AWS Toolkit**.

![aws](/static/aws-icon.png)

2. Open the IoT Section and then click on the **+** symbol next to **Certificates** and then select the new **local** folder you created. Then click **Save certificate here**.

![aws toolkit cert](/static/aws-tookit-cert.png)

3. Careate a new file in the **local** directory by right clicking on **local** and selecting **New File**. Name the file **policy.json**.

![local new file](/static/local-new-file.png)

Insert the following text into policy.json file: 

**Note:**

**The policy shown here is only for demonstration.**
**A production policy should follow best practices to restrict permissions to only what is necessary for you application**

```text
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "iot:*",
            "Resource": "*"
        }
    ]
}
```

4. Reopen the AWS Toolkit and create a new policy by clicking the **+** symbol next to **Policies** and selecting the **policy.json** file. Give the policy a name (e.g. **MyIotPolicy**)

![create policy](/static/create-policy.png)

5. Create a new thing. Select the **+** symbol next the **Things**. A prompt will appear to provide a name for your new thing.

![new thing](/static/new-thing.png)

6. Now attach the new policy to the **thing** and activate the new certificate.

![attach policy](/static/cert-attach-policy.png)

