---
title : "Lab 4: Moving your project to Keil Studio Cloud (KSC) (Step x)"
weight : 99
---

## Add Custom Tasks

- Add a task for the IDE to run the edit-creds.sh script
- Type Ctrl-Shift-P (or Cmd-Shift-P on a Mac) 
- Search for Tasks: Configure Tasks (Global)
- A new editor tab will open with /user/tasks.json
- Copy the contents of ./certs/tasks.json in to /user/tasks.json

![create tasks](/static/create_tasks.png)

- Execute the "edit-creds" task. Ctrl-Shift-P -> Tasks: Run task - edit-creds
