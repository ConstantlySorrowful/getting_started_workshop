---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Step 6)"
weight : 6
---

### Edit code changes

Now we can edit a change to our code, build, test, and finally save our changes back to our GitHub repo.

1. Open ./amazon-freertos/demos/coreMQTT/mqtt_demo_mutual_auth.c in the editor. Then scrool to about line 972. You should see the function **prvMQTTPublishToTopic()**

2. Insert a trivial code change. (e.g. At line ~986 replace: **mqttexampleMESSAGE** with a new string **"Hello, Constantly Sorrowful"**)

![u5 edit hello](/static/u5_edit_hello.png)

3. Rebuild the project to confirm the code change has not introduced an error.

You will notice when you run the code that the output string is shorter than expected. This is because the code change did not update the string length at line 987. (Unless you caught the mistake and fixed it yourself!)

### Commit to Github repository

4. Stage your changes by selecting the **Source Control** icon on the left and the clicking the **+** symbol next to the **mqtt_demo_mutual_auth.c** file.

**Only stage and commit the single file. Although other files will have been changed, these should not be committed to your repo with confidential configuration values. Your repo is public and anyone can see your secrets!**

![u5 stage](/static/u5_stage.png)

5. Commit your changes by entering a commit message describing your change in the text box and then clicking the checkmark symbol.

![ksc commit](/static/u5_commit.png)

6. Finally push your changes to GitHub by selecting the **...** dropdown menu and clicking **Push**.

![ksc push](/static/u5_push.png)

### Lab Summary

In this lab we have imported a project from GitHub into Keil Studio Cloud. We have compiled the code and deployed it to the STM32U5 board connected to the USB port of our PC. The project is then edited and changes saved in GitHub. Debugging is enabled directly within the browser IDE.