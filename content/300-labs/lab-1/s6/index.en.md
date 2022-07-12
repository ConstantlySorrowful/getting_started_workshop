---
title : "Lab 1: Launch an EC2 Instance with AVH AMI (Optional: Step 6)"
weight : 16
---

You can also use VS Code with the Remote SSH Extension to access the EC2 instance. If you already have VS Code installed on you workstation this extension will provide a better experience for editing files in later labs. 

To install the extension select the extensions icon along the left side. ![vscode icon](/static/vscode-ext-icon.png)

Search for remote ssh. It should be the first one in the list of similar extensions. Select the install button.

![avh_overview](/static/vscode-ssh.png)

After installing the extension you will see the **Open a Remote Window** icon in the bottom left corner.
![remote icon](/static/vscode-rem-ssh-icon.png)

Click the icon and then select **Connect to Host** or **Connect Current Window to Host**.

![vscode connect](/static/vscode-connect.png)

You can then choose to enter you connection command directly or edit you ssh config file (e.g. $HOME/.ssh/config)

Add an entry in your $HOME/.ssh/config file similar to this:

```
Host avh
  HostName 54.224.224.183
  User ubuntu
  IdentityFile ~/.ssh/avh-keypair.pem
```
Make sure to update the IP address to match your EC2 instance address.
