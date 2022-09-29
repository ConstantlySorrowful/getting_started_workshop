---
title : "Lab 7: Working With STM32U5 in Keil Studio Cloud (KSC) (Step 5)"
weight : 5
---

### Build

1. Connect you STM32U5 board via USB cable to your PC. Then select from the dropdown list for **Target Hardware**: **WiFi (STM32U585AIIx)**

2. Then click the **Build** button.

- The build should complete without errors.

![build ksc](/static/build_ksc.png)

### Run

3. Finally, run the project on the AVH model clicking the run button:

![run ksc](/static/run_ksc.png)

This will download the binary image to your connected U5 board.

### Output

4. Connect a terminal program to your serial port. On windows you can use Putty, TeraTerm, etc. Configure as baud rate: 115,200, 1 stop bit, no parity.

After the download completes the board should reset automatically and you should see output on the terminal program showing connecting to WiFi and AWS. The begin sending **"Hello World"** mqtt messages.

The Output panel will show the emulator running and connecting to AWS IoT Core.
