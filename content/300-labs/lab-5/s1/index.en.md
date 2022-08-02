---
title : "Lab 5: Using Device Shadows (Step 1)"
weight : 1
---

The GitHub repository used for this workshop contains several branches. To use the AWS IoT Device Shadows example you will need to checkout the **shadows** branch. Currently KSC does not provide a builtin procedure to change branches. However, a custom task can be used to help. 

- Open ./scripts/tasks.json and copy the contents
- Press Ctrl-Shift-P (or Command-Shift-P on Mac) and search for **Task: Configure Tasks...**
- Copy the buffer contents into new file.

Now you can use the **bash** task to switch branches.

- Press Ctrl-Shift-P and search for **Task: Run Task...**
- Select **bash** and then press enter.
- A new panel will open and you can enter shell commands
- At the command prompt enter:

```bash
cd /home/studio/workspace/avh-workshop
git checkout shadows
```

- You can confirm the branch has changed to **shadows** by entering:

```bash
git branch
```

 Also by looking in ./config_files/aws_demo_config.h
- About line 48 you should see: #define CONFIG_DEVICE_SHADOW_DEMO_ENABLED

