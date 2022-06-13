---
title : "Lab 2: Building and running code with AVH (Step 2)"
weight : 2
---

## Install latest version of cmsis-toolbox utilities

Depending on the AMI version selected whe you launched the EC2 instance, you may want to update the cmsis-toolbox utilities.

Check for latest version here: https://github.com/Open-CMSIS-Pack/devtools/releases

At this time the latest version is: 0.10.2. I recommend creating a $HOME/bin directory. Then download and unpack the file there. Also add the location to your PATH environment variable.

```
mkdir -p $HOME/bin
cd $HOME/bin
rm -rf cmsis-toolbox-linux64*
wget https://github.com/Open-CMSIS-Pack/devtools/releases/download/tools%2Ftoolbox%2F0.10.2/cmsis-toolbox-linux64.tar.gz
tar xzf cmsis-toolbox-linux64.tar.gz
echo 'PATH=$HOME/bin/cmsis-toolbox-linux64/bin:$PATH' >> $HOME/.bashrc
```

You will need to logout and back in or source the $HOME/.bashrc file to apply the PATH variable change.
