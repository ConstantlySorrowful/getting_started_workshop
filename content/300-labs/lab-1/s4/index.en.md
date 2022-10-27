---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Step 4)"
weight : 4
---

### Edit Configuration

To update our configuration files, we to add some additional helper files to our local folder.

1. Select the local folder again and right-click to create a new file. Name the file **config.txt**.

2. Add the following contents to the file. And then complete each line with the unique values for you account. If building for a virtual target, the WiFi values are not needed.

**(Note: Do not leave a space after the '=' symbol.)**

```text
export MQTT_BROKER_ENDPOINT=
export IOT_THING_NAME=
export WIFI_SSID=
export WIFI_PASSWORD=
```

3. Create another file in the **local** folder and name it **tasks.json**.

4. Add the following contents to the file.

```json
{
	// See https://go.microsoft.com/fwlink/?LinkId=733558
	// for the documentation about the tasks.json format
	"version": "2.0.0",
	"tasks": [
        {
            "label": "bash",
            "type": "process",
            "args": [
                "-l"
            ],
            "command": "/bin/bash",
            "presentation": {
                "echo": false,
                "focus": true,
                "group": "build",
                "panel": "dedicated"
            },
            "problemMatcher": []
        },
        {
            "label": "creds",
            "type": "shell",
            "command": "/home/studio/workspace/aws_mqtt_mutualauth_demo/certs/edit-creds.sh",
            "options": {
                "cwd": "/home/studio/workspace/aws_mqtt_mutualauth_demo/certs"
            },
            "problemMatcher": []
        }
    ]
}
```

5. Create another file in the **local** folder and name it **edit-creds.sh**.

6. Add the following contents to the file.

```bash
#!/bin/bash
export PATH="$PWD:$PATH"
#echo $PATH
cert=`ls /home/studio/workspace/local/*-cert*`
priv=`ls /home/studio/workspace/local/*-priv*`
sed -z 's/\n/\\n/g;s/^/export CLIENT_CERTIFICATE_PEM=\"/;s/\(export CLIENT_CERT.*\)\\n$/\1\"\n/' $cert > cert.str
sed -z 's/\n/\\n/g;s/^/export CLIENT_PRIVATE_KEY_PEM=\"/;s/\(export CLIENT_PRIV.*\)\\n$/\1\"\n/' $priv > priv.str
cat cert.str >> secrets.txt
cat priv.str >> secrets.txt

source secrets.txt 
cd ../amazon-freertos/demos/include
envsubst <aws_clientcredential.h.in >aws_clientcredential.h
envsubst <aws_clientcredential_keys.h.in >aws_clientcredential_keys.h

cd -
cd ../Socket/WiFi
envsubst <socket_startup.c.in >socket_startup.c
```

1. Return to the **Expolrer** view and expand the **local** folder. The certificate created earlier and saved in the **local** folder will have generated 3 files. Each beginning with a long hash value. Open the file ending with **-certificate.pem.crt**. Copy the full contents into copy buffer (Ctrl-C).

![explorer](/static/explorer-view2.png)


3. Open the project file ./amazon-freertos/demos/include/aws_clientcredential_keys.h

Open the **** file in the editor window and append each line with values for your environment.

![edit secrets](/static/edit-secrets.png)

3. Add a **task** to the IDE to help us apply these configuration items into the code. Open the **tasks.json** file and select all the text. Then use Ctrl-C (or CMD-C on a Mac) to copy the text to the copy buffer. 

Press Ctrl-Shift-P to open the Command tool and search for **Task: Configure Tasks...**. This will open a new **tasks.json** file. (A system file.) Paste the contents of the copy buffer into the new **tasks.json** file window. (Ctrl-V). This is adding 2 new tasks to the IDE. (**creds** and **bash**)

![](/static/config-tasks.png)

4. Now you can run the **creds** task using Ctrl-Shift-P again. This time searching for **Task: Run Task...** and then selecting the **creds** task. This will apply the config values to the code before building and running.

An additional **task** is also added to open a **bash** shell if needed.

