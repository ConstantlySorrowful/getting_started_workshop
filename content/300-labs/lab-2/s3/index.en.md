---
title : "Lab 2: Launch an EC2 Instance with AVH AMI (Step 3)"
weight : 3
---

On this page there are several selection options. For the Action, **Launch from Website** is the default. Select **Launch through EC2** from the dropdown list.


![avh_overview](/static/marketplace-11.png)

1. On the EC2 Launch configuation page give the new instance a name.

![avh_overview](/static/marketplace-12.png)

2. Then scroll down and select a key pair from any you may already have defined or create a new pair.

![avh_overview](/static/marketplace-13.png)

3. Scroll to the bottom and expand the **Advanced details** section.

![avh_overview](/static/marketplace-14.png)

4. Scroll to the bottom of the **Advanced details** section until you find the **User data** input field.
![avh_overview](/static/marketplace-15.png)

5. Enter the following script into the **User data** field and then select **Launch instance**

```bash
#!/bin/bash -x
exec > /home/ubuntu/userdata.log 2>&1
cd /home/ubuntu
source /etc/profile.d/avh.sh
wget https://github.com/Open-CMSIS-Pack/cmsis-toolbox/releases/download/1.2.0/cmsis-toolbox-linux64.tar.gz
cd /opt
tar xzf /home/ubuntu/cmsis-toolbox-linux64.tar.gz
mv ctools ctools.save
ln -s cmsis-toolbox-linux64 ctools
cd ctools/etc
sed -i 's/set(TOOLCHAIN_ROOT ".*/set(TOOLCHAIN_ROOT "\/opt\/armcompiler\/bin")/' AC6.6.18.0.cmake
PATH=/opt/ctools/bin:$PATH
echo "cpackget: $(which cpackget)"
echo "cpackget version: $(cpackget --version)"
echo "csolution: $(which csolution)"
echo "csolution version: $(csolution --version)"
echo "cbuild: $(which cbuild)"
echo "cbuild version: $(cbuild --version)"
```

![avh_overview](/static/marketplace-16.png)
