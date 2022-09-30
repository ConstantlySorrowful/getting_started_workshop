---
title : "Lab 7: Working With STM32U5 in Keil Studio Cloud (KSC) (Step 4)"
weight : 4
---

### Edit Configuration

1. Return to the **Expolrer** view and expand the **certs** folder.

![explorer](/static/explorer-view.png)

2. Open the **secrets.txt** file in the editor window and append each line with values for your environment.

![edit secrets](/static/edit-secrets.png)

3. Add a **task** to the IDE to help us apply these configuration items into the code. Open the **tasks.json** file and select all the text. Then use Ctrl-C (or CMD-C on a Mac) to copy the text to the copy buffer. 

Press Ctrl-Shift-P to open the Command tool and search for **Task: Configure Tasks...**. This will open a new **tasks.json** file. (A system file.) Paste the contents of the copy buffer into the new **tasks.json** file window. (Ctrl-V). This is adding 2 new tasks to the IDE. (**creds** and **bash**)

![](/static/config-tasks.png)

4. Now you can run the **creds** task using Ctrl-Shift-P again. This time searching for **Task: Run Task...** and then selecting the **creds** task. This will apply the config values to the code before building and running.

An additional **task** is also added to open a **bash** shell if needed.

