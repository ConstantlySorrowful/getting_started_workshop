---
title : "AWS IAM Role"
weight : 2
---

### IAM - Create an Instance Role

We will also need an EC2 instance Role. This allows EC2 instances to call AWS services on your behalf.

Open the AWS Console in your browser and navigate to the IAM service page. 

- Select Roles from the left column
- Click Create role
- For Trusted entity type, select AWS service
- Under common use cases, select EC2
- Click Next

![create-role](/static/create-role.png)

- Add the following permissions:
    - AmazonS3FullAccess
    - AmazonSSMManagedInstanceCore
    - AmazonSSMFullAccess
- And add Permission boundary:
    - PowerUserAccess

Ensure the Trust Relationship looks like this:
```
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

![create-role](/static/create-role.png)

Next give your Role a name and then click the Create role button at the bottom of the page.
