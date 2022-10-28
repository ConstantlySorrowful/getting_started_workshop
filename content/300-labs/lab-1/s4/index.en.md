---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Step 4)"
weight : 4
---

### Edit Configuration

To update our configuration files, we will use the additional files added to **local** from the S3 bucket earlier.

1. Select the local folder again and open the file **config.txt**. Complete line with values from your own account.


**(Note: Do not leave a space after the '=' symbol.)**

```text
export MQTT_BROKER_ENDPOINT=
export IOT_THING_NAME=
export WIFI_SSID=
export WIFI_PASSWORD=
```

2. Add a **task** to the IDE to help us apply these configuration items into the code. Open the **tasks.json** file in **local** and select all the text. Then use Ctrl-C (or CMD-C on a Mac) to copy the text to the copy buffer. 

3. Press Ctrl-Shift-P to open the Command selection tool and search for **Task: Configure Tasks...**. This will open a new **tasks.json** file. (Global) Paste the contents of the copy buffer into the new **tasks.json** file window. Replace any text already in this file. (Ctrl-V). This is adding 2 new tasks to the IDE. (**edit-creds** and **bash**)

![](/static/config-tasks.png)

4. Now you can run the **edit-creds** task using Ctrl-Shift-P again. This time searching for **Task: Run Task...** and then selecting the **edit-creds** task. This will apply the config values to the code before building and running. 

You won't see any output from running the command, but you can verify it completed by checking the contents of one of the source code files in ./aws_mqtt_mutualauth_demo/amazon-freertos/demos/include/aws_client_credential.h

![verify](/static/verify-code.png)


An additional **task** is also added to open a **bash** shell if needed.


