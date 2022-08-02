---
title : "Lab 6: Creating and Deploying Jobs (Step 1)"
weight : 1
---

The GitHub repository used for this workshop contains several branches. To use the AWS IoT Device Jobs example you will need to checkout the **jobs** branch. Currently KSC does not provide a builtin procedure to change branches. However, a custom task can be used to help. 

## If you have installed the tasks.json file in the previous lab skip to #8.

1. Open ./scripts/tasks.json and copy the contents
2. Press Ctrl-Shift-P (or Command-Shift-P on Mac) and search for **Task: Configure Tasks...**
3. Copy the buffer contents into new file.

Now you can use the **bash** task to switch branches.

4. Press Ctrl-Shift-P and search for **Task: Run Task...**
5. Select **bash** and then press enter.
6. A new panel will open and you can enter shell commands
7. At the command prompt enter:

8. Enter shell commands.

```bash
cd /home/studio/workspace/avh-workshop
git checkout jobs
```

9. You can confirm the brach has changed to **jobs** by entering:

```bash
git branch
```

 Also by looking in ./config_files/aws_demo_config.h
- About line 48 you should see: #define CONFIG_JOBS_DEMO_ENABLED
