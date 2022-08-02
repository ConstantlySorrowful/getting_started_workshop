---
title : "Lab 4: Moving your project to Keil Studio Cloud (KSC) (Step 4)"
weight : 4
---

### Build

1. Select from the dropdown list for **Target Hardware**: **Corestone-SSE-300**

2. Then click the **Build** button.

- The build should complete without errors.

![build ksc](/static/build_ksc.png)

### Run

3. Finally, run the project on the AVH model clicking the run button:

![run ksc](/static/run_ksc.png)

### Stop

4. After letting the program run briefly you can stop it by pressing Ctrl-Shift-P (Or Cmd-Shift-P on a Mac) and selecting **Stop all VHT run jobs**


![stop ksc](/static/stop-ksc.png)

### Output

The Output panel will show the emulator running and connecting to AWS IoT Core.

![ksc output](/static/ksc_output.png)
