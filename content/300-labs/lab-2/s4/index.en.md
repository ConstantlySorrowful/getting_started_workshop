---
title : "Lab 2: Building and running code with AVH (Step 4)"
weight : 4
---

## Build and run the code

Now that you have completed the following:

- Creating a Thing in AWS Console
- Creating a policy and certificate
- Uploading the certificate and private key to the EC2 instance
- Editing the credentials configuration files

You can now build the project using the cmsis-toolbox utility 'cbuild'.

```
cd $HOME/AVH_Labs
cbuild.sh demo.VHT_MPS3_Corstone_SSE-300.cprj
```
You should see many lines of compiling scroll past, but at the end you should see:

```
cbuild.sh finished successfully!
```

It is time to run the image using the AVH emulator. Before starting the emulator, open the AWS Console and navigate to the IoT Core service page. From the left column, select the MQTT test client. Enter a topic filter '#' and then expand the Additional configuration list. Choose 'Display payloads as strings (more accurate)' and then click Subscribe. Keep this tab open in your browser to see MQTT messages sent from the application.

Now return to the shell in the EC2 instance and execute the following code. Or run ./scripts/run300.sh

```
cd $HOME/AVH_Labs
VHT_MPS3_Corstone_SSE-300 \
-C mps3_board.visualisation.disable-visualisation=1 \
-C mps3_board.telnetterminal0.start_telnet=0 \
-C mps3_board.uart0.out_file=- \
-a Objects/image.axf
```

After the emulator starts and loads the image file, you will see messages begin to scroll up.
Watch the MQTT test client log in the browser. After the demo completes, you can press Ctrl-C in the shell to terminate the emulator.
