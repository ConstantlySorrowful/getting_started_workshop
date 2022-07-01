---
title : "Lab 5: Using Device Shadows (Step 2)"
weight : 2
---

Switching between branches should retain the changes made to the credentials files. Confirm by checking ./amazon-freertos/demos/include/aws_clientcredential.h and aws_clientcredential_keys.h to verify your changes have not been lost.

Now you can build the Shadows demo application.

## Build

- **Build** the project by clicking the build button: ![Build Button](/static/build_button.png)
- The build should complete without errors. 
- Finally, run the project on the AVH model clicking the run button: ![Run Button](/static/run_button.png)
- You will see the debug messages in the **Output** window:
- This time you will see the application subscribing to Shadow reserved topic and detecting updates.
- We will examine the details of Shadow updates in a later lab.
 
