---
title : "Lab 7: Working With STM32U5 in Keil Studio Cloud (KSC) (Step 6)"
weight : 6
---

### Edit code changes

Now we can edit a change to our code and trigger the GitHub actions to launch a build/test exectution.

1. Open the app_main.c file in the editor window.

2. Insert a trivial code change. (e.g. At line ~59 insert: status = -1;)

![build ksc](/static/ksc_edit.png)

3. Rebuild the project to confirm the code change has not introduced an error.

### Commit to Github repository

4. Stage your changes by selecting the **Source Control** icon on the left and the clicking the **+** symbol next to the app_main.c file.

![ksc stage](/static/ksc-stage.png)

5. Commit your changes by entering a commit message describing your change in the text box and then clicking the checkmark symbol.

![ksc commit](/static/ksc-commit.png)

6. Finally push your changes to GitHub by selecting the **...** dropdown menu and clicking **Push**.

![ksc push](/static/ksc-push.png)

You will now be able to see a new EC2 launch in AWS Console and also see the GitHub action triggered.

### Lab Summary

In this lab we have imported the same project we were using in the EC2 instance. The project is saved in GitHub and can be built and tested in either EC2 or KSC. With git command support built into KSC the same CI/CD workflow is also triggered in KSC by simply commiting and pushing code changes.

