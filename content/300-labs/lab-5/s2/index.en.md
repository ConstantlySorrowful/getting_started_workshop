---
title : "Lab 5: Using Device Shadows (Step 2)"
weight : 2
---

Switching between branches should retain the changes made to the credentials files. Confirm by checking ./amazon-freertos/demos/include/aws_clientcredential.h and aws_clientcredential_keys.h to verify your changes have not been lost.

Now you can build the Shadows demo application. You use the same steps as in the previous lab to **Build/Run/Stop**

## Build

1. **Build** the project by clicking the build button: 

![Build Button](/static/build_button.png)

2. The build should complete without errors. 

## Run

3. Finally, run the project on the AVH model clicking the run button: 

![Run Button](/static/run_button.png)

4. You will see the debug messages in the **Output** window:

5. This time you will see the application subscribing to Shadow reserved topic and detecting updates.

## Test

6. You can optionally confirm by opening the AWS Console -> MQTT Test client and subscribe to topic '#'.

![mqtt test client](/static/mqtt-test-client.png)


### Lab Summary

In this lab we have selected a different branch in the git repository to examine **AWS IoT Device Shadows**. You then rebuilt the project in KSC. With git command support built into KSC the same CI/CD workflow is also triggered in KSC by simply commiting and pushing code changes. The GitHub actions will trigger, but will fail the test case because the build.py script has not been updated to handle different output. **(Try this yourself)**

