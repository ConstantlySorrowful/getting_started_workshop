---
title : "Lab 3: Building and running code with AVH (Step 8)"
weight : 8
---

## Build and run the code

You can now build the project using the cmsis-toolbox utilities **csolution** and **cbuild**.

```bash
cd $HOME/AWS_MQTT_MutualAuth_Demo
csolution convert -s Demo.csolution.yml
cbuild Demo.Debug+AVH.cprj
```
You should see many lines of compiling scroll past, but at the end you should see:

```
cbuild finished successfully!
```

It is time to run the image using the AVH emulator. Before starting the emulator, open the AWS Console in your browser and navigate to the IoT Core service page. 

1. From the left column, select the MQTT test client. 

![iot-mqtt 1](/static/iot-core-mqtt-1.png)

2. Enter a topic filter '#' and then expand the Additional configuration list. 
3. Choose 'Display payloads as strings (more accurate)' and then click Subscribe.

![iot-mqtt 2](/static/iot-core-mqtt-2.png)

Keep this tab open in your browser to see MQTT messages sent from the application.

Now return to the shell in the EC2 instance and execute the following code.

```bash
cd $HOME/AWS_MQTT_MutualAuth_Demo
VHT_MPS3_Corstone_SSE-300 \
-C mps3_board.visualisation.disable-visualisation=1 \
-C mps3_board.telnetterminal0.start_telnet=0 \
-C mps3_board.uart0.out_file=- \
-a /home/ubuntu/AWS_MQTT_MutualAuth_Demo/out/Demo/AVH/Debug/Demo.Debug+AVH.axf
```

After the emulator starts and loads the image file, you will see messages begin to scroll up.
Watch the MQTT test client log in the browser. After the demo completes, you can press Ctrl-C in the shell to terminate the emulator.


## Lab summary

In this lab there many setup steps needed:

- Creating a Thing in AWS Console
- Creating a policy and certificate
- Uploading the certificate and private key to the EC2 instance
- Collected the settings values
- Editing the credentials configuration files

These were necessary before running the application, however you will now be able to automate the workflow in the next lab.
