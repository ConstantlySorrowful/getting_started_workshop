---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Using STM32U585 - Step 5)"
weight : 5
---

### Build

1. Connect your STM32U5 board via USB cable to your PC. Then select from the dropdown list for **Target Hardware**: **WiFi (STM32U585AIIx)**


2. Open the project file **./aws_mqtt_mutualauth_demo/Socket/WiFi/socket_startup.c** and set the correct values for **SSID** and **PASSWORD** needed for you local WiFi network.

![set ssid](/static/socket_ssid.png)

3. Then click the **Build** button.

- The build should complete without errors.

![build u5](/static/build_u5.png)

### Run/Debug

4. Finally, run or debug the project on the STM32U5 board connected via USB by clicking the run or debug buttons:

![run u5](/static/run_u5.png)

This will download the binary image to your connected U5 board. If you selected debug it will load the **main** function and allow you to begin stepping through the code with the debugger.

![debug u5](/static/debug_u5.png)

### Output

5. Connect a terminal program to your serial port. On windows you can use Putty, TeraTerm, etc. Configure as baud rate: 115,200, 1 stop bit, no parity.

After the download completes the board should reset automatically and you should see output on the terminal program showing connecting to WiFi and AWS. The begin sending **"Hello World"** mqtt messages.

### Lab Summary

In this lab we have imported a project from GitHub into Keil Studio Cloud. We have compiled the code and deployed it to both a virtual target and then the STM32U5 board connected to the USB port of our PC. The only change needed was to add the correct SSID and PASSWORD for connecting to your local network.
