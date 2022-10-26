---
title : "Lab 7: Creating and Deploying Jobs (Step 3)"
weight : 3
---

## Create a Job document

1. On your local P.C. create a new text file. (Notepad, gedit, vim, etc.)

Insert the following JSON contents:

```bash
{ "action": "publish", "topic": "demo/jobs", "message": "Hello from AVH!" }
```
2. Save the file as **avh-workshop-job.json**

## Upload to your S3 bucket.

3. Navigate to S3 service page and select the bucket you created earlier. Then click **Upload**.

![upload job doc 1](/static/upload-job-doc.png)

4. Click **Add files** and find the file saved on your local PC.
![upload job doc 2](/static/upload-job-doc-2.png)
