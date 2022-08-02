---
title : "Lab 6: Creating and Deploying Jobs (Step 2)"
weight : 2
---

Switching between branches should retain the changes made to the credentials files. Confirm by checking ./amazon-freertos/demos/include/aws_clientcredential.h and aws_clientcredential_keys.h to verify your changes have not been lost.

Now you can build the Jobss demo application. You use the same steps as in the previous lab to **Build/Run/Stop**

## Build

1. **Build** the project by clicking the build button: 

![Build Button](/static/build_button.png)

2. The build should complete without errors. 

3. Finally, run the project on the AVH model clicking the run button: 

![Run Button](/static/run_button.png)

4. You will see the debug messages in the **Output** window:

5. This time you will see the application initiating a jobs task waiting for a new job request. You will create a job request in the next step.

