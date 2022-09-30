---
title : "Lab 7: Working With STM32U5 in Keil Studio Cloud (KSC) (Step 5)"
weight : 5
---

### Build

1. Connect you STM32U5 board via USB cable to your PC. Then select from the dropdown list for **Target Hardware**: **WiFi (STM32U585AIIx)**

2. Then click the **Build** button.

- The build should complete without errors.

![build u5](/static/build_u5.png)

### Run/Debug

3. Finally, run or debug the project on the STM32U5 board connected via USB byclicking the run or debug buttons:

![run u5](/static/run_u5.png)

This will download the binary image to your connected U5 board. If you selected debug it will load the **main** function and allow you to begin stepping through the code with the debugger.

![debug u5](/static/debug_u5.png)

### Output

4. Connect a terminal program to your serial port. On windows you can use Putty, TeraTerm, etc. Configure as baud rate: 115,200, 1 stop bit, no parity.

After the download completes the board should reset automatically and you should see output on the terminal program showing connecting to WiFi and AWS. The begin sending **"Hello World"** mqtt messages.
