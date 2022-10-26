---
title : "Lab 7: Creating and Deploying Jobs (Step 4)"
weight : 4
---

## Create a Job

1. Open the AWS Console in your browser and navigate to **AWS Iot -> Manage -> Remote Actions -> Jobs**. Click the **Create job** button.

![create job 1](/static/create-job-1.png)

2. Select **Create custom job** and click **Next**.

![create job 2](/static/create-job-2.png)

3. Give your job a name and optionally add a description. Click **Next**.

![create job 3](/static/create-job-3.png)

4. From the dropdown list you should see your configured device. Select the device.

![create job 4](/static/create-job-4.png)

5. Select the job document you uploaded to your S3 bucket. Use the **Browse S3** button to find it.

![create job 5](/static/create-job-5.png)

6. Select **Snapshot** and then click **Submit**.

![create job 6](/static/create-job-6.png)

7. Return to Keil Studio Cloud tab in your browser. You may need to restart your application. (It may have timeout by now.)

8. Check **Output** panel for success.

![job output](/static/job-output.png)

9. Also confirm Job completion in AWS Console.

![job output 2](/static/job-output-2.png)


### Lab Summary

In this lab we have selected a different branch in the git repository to examine **AWS IoT Device Jobs**. You then rebuilt the project in KSC. With git command support built into KSC the same CI/CD workflow is also triggered in KSC by simply commiting and pushing code changes. The GitHub actions will trigger, but will fail the test case because the build.py script has not been updated to handle different output. However, this labs also requires a job creation and deployment step. This is also not automated at this time. In future labs we can extend the CI/CD workflow to include this automation.

