---
title : "AWS IAM Role"
weight : 2
---

### IAM - Create an Instance Role

You will also need an EC2 instance Role. This allows EC2 instances to call AWS services on your behalf.

Open the AWS Console in your browser and navigate to the IAM service page. 

- Select Roles from the left column
- Click Create role

![create role 1](/static/create-role-1.png)

- For Trusted entity type, select AWS service
- Under common use cases, select EC2
- Click Next

![create-role 2](/static/create-role-2.png)

- Add the following permissions: 

  Use search field at the top to find each and select the checkbox. You will need to **Clear filters** to find the next.

    - AmazonS3FullAccess
    - AmazonSSMManagedInstanceCore
    - AmazonSSMFullAccess

- Set Permission boundary: (Use a permissions boundary to control the maximum role permissions)
    - PowerUserAccess

Then click **Next**.

![create-role 3](/static/create-role-3.png)

- Next give your Role a name

- Ensure the Trust Relationship looks like this:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Service": "ec2.amazonaws.com"
            },
            "Action": "sts:AssumeRole"
        }
    ]
}
```

 and then click the **Create role** button at the bottom of the page.

![create-role 6](/static/create-role-6.png)

