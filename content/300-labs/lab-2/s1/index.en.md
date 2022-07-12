---
title : "Lab 2: Building and running code with AVH (Step 1)"
weight : 1
---


## Use SSH Command to Connect to EC2 Instance

If you have stopped your EC2 instance after completing the previous lab, go to the AWS Console in your browser and open the EC2 service page. Then select the instance you created in Lab-1 and set the **Instance state** to start.

![instance_restart](/static/restart-ec2.png)

Wait until the instance has completed startup and then open a terminal application or use VSCode to connect.

```
$ ssh -i /path/to/avh-keypair.pem ubuntu@<public.ip.addr>
```

Alternatively, you can use VSCode to connect.

![vscode-ssh](/static/vscode-ssh-2.png)
