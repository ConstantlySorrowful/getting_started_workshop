---
title : "Cleanup"
weight : 400
---

# Shutdown and Cleanup AWS and Github Resources

- Be sure to Stop or Terminate EC2 instances used in the workshop.
  - [Terminate your instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html)

- Check your repositories in GitHub to confirm you have not committed/pushed
  any credentials or ANY other sensitive data.
  - (e.g. aws_clientcredential.h and aws_clientcredential_keys.h)

- Empty or delete the S3 bucket used in this workshop.
  - [Deleting a bucket](https://docs.aws.amazon.com/AmazonS3/latest/userguide/delete-bucket.html)