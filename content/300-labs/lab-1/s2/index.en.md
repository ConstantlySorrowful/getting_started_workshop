---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Step 2)"
weight : 2
---

The project is imported and set as the active project:
  ![AWS MQTT Demo project opened and set active](/static/avh_in_ksc2.png)

## Create a new folder

1. Create a new folder outside you project where you can keep files not specific to your project. Name this new folder **local**. Right click in the blank area of the Explorer section of the IDE to open the menu. Select **New Folder**.

![local folder](/static/local-folder.png)

## Copy files from S3 Bucket

We will connect to an S3 bucket to dowload additional resource files into the **local** folder.

2. Click the **AWS** icon on the left side of the IDE window to open the **AWS Toolkit**.

![aws](/static/aws-icon.png)

3. Edit credentials profile by selecting **More Actions** eliplsis and then **Choose AWS Profile**. Then select **Edit Credentials**.

![aws tk 3](/static/aws-tk-3.png)
![aws tk 2](/static/aws-tk-2.png)

## Create a second AWS profile for access to workshop resources.

4. Insert the following text below the default profile in the credentials file.

```text
[avh]
aws_access_key_id = XXXXXXXXXXXXXXXXXXXX
aws_secret_access_key = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

And add this text to the config file.

```text
[avh]
region = us-east-1
output = json
```

![profile 2](/static/profile-2.png)

5. Now return to edit credentials profile by selecting **More Actions** eliplsis and then **Choose AWS Profile**. This time select **avh profile**.


6. Confirm the region showing is set correctly. If needed you can right click on the current region and select **Show or Hide Regions** and then from the dropdown list select the correct region.

![aws tk 1](/static/aws-tk-1.png)

7. Expand the S3 section of the AWS Toolkit and find the **avh-workshop-extras** bucket.

![workshop folder](/static/workshop-folder.png)

8. For each file in the folder, select the download icon on the right side of the file name and then choose to put it into the path **/home/studio/workspace/local**.

![workshop folder 2](/static/workshop-folder-2.png)

