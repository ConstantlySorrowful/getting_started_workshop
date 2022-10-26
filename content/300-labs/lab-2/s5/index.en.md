---
title : "Lab 2: Launch an EC2 Instance with AVH AMI (Optional: Step 5)"
weight : 5
---

**(Window - Putty)**

If you have created a new ssh key (e.g. avh-keypair.pem in step 3) you must import it into putty key format. Open the **PuttyGen** application and select the **Conversions** tab and choose **Import** key.

If you want to use a key-pair you had previously uploaded to your AWS account, you should be able to find the file in your local user directory (e.g. C:\Users\<username>\.ssh\id_rsa. **Note: This is the default location, however you may have generated them into a different location if you setup another ssh client previously.**)

![Putty Import](/static/putty-import.png)

After importing the key click the **Save private key** button with file extension .ppk (e.g. avh-keypair.ppk)

![Putty Save](/static/putty-save.png)

Now open the **Putty** application and enter the public IP address in the Session configuration. Also ensure the connection type is set to SSH.

![Putty Session](/static/putty-session.png)

Then scroll down to the Connection -> SSH -> Auth configuration page. At the bottom click the browse button and find the saved ppk file. (Be sure to select the .ppk file instead of the .pem file.)

![Putty Auth](/static/putty-auth.png)

Now click the open button and you should see a new session window open and a prompt for **login as:**. Enter **ubuntu**.

![Putty Login](/static/putty-login.png)

You should now see your console connection to the EC2 instance open.
