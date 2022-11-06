---
title : "Lab 4: Automate with GitHub Actions CI/CD Workflows (Step 2)"
weight : 2
---

The workflow jobs and steps are contained in the following files:

- $HOME/avh-workshop/.github/workflows/c300_virtual_hardware.yml
- $HOME/avh-workshop/avh.yml
- $HOME/avh-workshop/build.py
- $HOME/avh-workshop/vht_config.txt

These can be modified later as needed to modify the configuration and add more test cases. For now you can keep them as-is.

Navigate to your repository in your browser and 

1. Select **Actions** from the top
2. Select the **Corestone 300 Arm Virtual Hardware** workflow.
3. Select the drop-down on the right labled **Run workflow**
4. Choose the main branch and run workflow. 

In the screenshot you will see a run has already completed. After you start your run, you will see a new workflow execution in your list. This will run for several minutes.

If you return to the AWS Console - EC2 service page, you will see a new EC2 instance starting up. This new instance will clone your repository, compile the project, and then run the application. It will then capture the console log and attach it to the results in GitHub. 

![actions](/static/actions.png)
