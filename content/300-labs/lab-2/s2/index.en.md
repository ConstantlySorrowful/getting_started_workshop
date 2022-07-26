---
title : "Lab 2: Building and running code with AVH (Step 2)"
weight : 2
---

## Install new cmsis-toolbox

Although the EC2 instance will already have CMSIS build tools installed, we will install a newer version for this workshop. Execute the shell code below in your terminal to complete these steps.

1. Download the current version and extract into $HOME/bin
2. Add the new tools directory to your PATH.
3. You will need to logout and back in for the new PATH setting.

```bash
mkdir -p $HOME/bin
cd $HOME/bin
wget https://github.com/Open-CMSIS-Pack/devtools/releases/download/tools%2Ftoolbox%2F0.10.2/cmsis-toolbox-linux64.tar.gz
tar xzvf cmsis-toolbox-linux64.tar.gz
echo 'PATH="$HOME/bin/cmsis-toolbox-linux64/bin:$PATH"' >> $HOME/.profile

```
**Note: VSCode server caches the environment. You will need to restart the vscode-server to pick up the new settings.**

## Install CMSIS-Packs

You will need several **CMSIS-Packs** installed for the workshop labs. Although some will have already been installed when the AMI was prepared, you can install any additional as needed using the **cpackget** command. The .cprj project file will also add any required packs so this script is not mandatory. This example of using **cpackget** is provided to show management of your pack repository. 

Create a script file to add the CMSIS-Packs we will need in the workshop.

```bash
mkdir -p $HOME/bin
cat << EOF > $HOME/bin/addcpacks.sh
#!/bin/bash
cpackget -q pack add -a ARM::CMSIS-Driver
cpackget -q pack add -a ARM::CMSIS-FreeRTOS@10.4.6
cpackget -q pack add -a ARM::mbedTLS@1.7.0
cpackget -q pack add -a AWS::backoffAlgorithm@1.0.0-Beta
cpackget -q pack add -a AWS::coreMQTT@1.1.0-Beta
cpackget -q pack add -a AWS::coreMQTT_Agent@1.0.1-Beta
cpackget -q pack add -a AWS::corePKCS11@3.0.0-Beta
cpackget -q pack add -a AWS::FreeRTOS-Plus-TCP@2.3.2-Beta
cpackget -q pack add -a Arm-Packs::PKCS11
cpackget -q pack add -a MDK-Packs::IoT_Socket
cpackget -q pack add -a Keil::V2M-MPS2_CMx_BSP@1.8.0
cpackget -q pack add -a ARM::V2M_MPS3_SSE_300_BSP@1.2.0
cpackget -q pack add -a NXP::MIMXRT1052_DFP@13.1.0
cpackget -q pack add -a NXP::EVKB-IMXRT1050_BSP@13.1.0
cpackget -q pack add -a Keil::IMXRT1050-EVKB_BSP@1.0.0
cpackget -q pack add -a Keil::iMXRT105x_MWP@1.4.0
cpackget -q pack add -a AWS::AWS_IoT_Device_Shadow@1.0.2-Beta
cpackget -q pack add -a AWS::coreJSON@3.0.0-Beta
cpackget -q pack add -a AWS::AWS_IoT_Jobs@1.1.0-Beta
cpackget -q pack add -a AWS::AWS_IoT_Device_Defender@1.1.0-Beta
EOF
chmod +x $HOME/bin/addcpacks.sh
$HOME/bin/addcpacks.sh
```
