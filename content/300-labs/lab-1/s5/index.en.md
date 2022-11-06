---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Step 5)"
weight : 5
---

### Build

1. Select the AVH target from the dropdown list for **Target Hardware**: **AVH (SSE-300-MPS3)**

![select target](/static/select-target.png)


2. Then click the **Build** button.

- The build should complete without errors and it will also download a binary image to your local PC. This file is not needed at this time.

![avh build](/static/avh-build.png)

### Run/Debug

3. Finally, run the project on the AVH virtual target.

![run avh](/static/run-avh.png)

You should now see the virtual target launch and begin to run the application. The output window sill show setting up an MQTT connection to your AWS account and begin publishing. It will also subscribe to the same topic to see the messages coming back.

