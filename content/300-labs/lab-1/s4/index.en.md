---
title : "Lab 1: Developing With Keil Studio Cloud (KSC) (Step 4)"
weight : 4
---

### Edit Configuration

KSC provides a method to create custome **tasks**. You can use custom tasks for adding special functions to automate repeating tasks. Here we will create a task to simple open a bash shell.

1. Press **Ctrl-Shift-P** to open the command tool. Search for Task: **Configure Tasks...**.

![config tasks](/static/config-tasks.png)

1. Create a new **Global** task using the following text. 

```json
{
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
        }
    ]
}
```

2. Also create a new file in the **local** folder. Name it **pem2str**. Insert the following text into this new file.


```bash
sed 's/^/"/;s/$/\\n" \\/' $1 > $1.str
```

3. Now open a bash shell by running the new task. Press **Ctrl-Shift-P** and search for **Task: Run Task...**. Select the **bash** task and a new panel will open at the bottom. In the **bash** shell, navigate to the **local** folder.

```bash
cd /home/studio/workspace/local
```

4. Add execute permission to the file **pem2str**.

```bash
chmod +x pem2str
```

5. Now execute the **pem2str** script to create modified versions of the certificate and private key files.

```bash
./pem2str <xxxxx>-certificate.pem.crt
./pem2str <xxxxx>-private.pem.key
```

6. Now open the new version of the certificate file. It is named the same as the original with **.str** appended. Select the full text into the copy buffer. (Ctrl-C)

7. Open the project file **./aws_mqtt_mutualauth_demo/amazon-freertos/demos/include/aws_clientcredential_keys.h** and scroll down untill you find the section defining the certificate.

    #define keyCLIENT_CERTIFICATE_PEM    \

Insert the copied text below this line. (Yours will not match this.)

![cert string](/static/cert-string.png)

8. Scroll down further until you find the private key section.

    #define keyCLIENT_PRIVATE_KEY_PEM    \

Copy/paste from the modified version of the private key file ( with .str appended) in the **local** folder below this line.

![private-key](/static/private-key.png)

9. Now open the file **./aws_mqtt_mutualauth_demo/amazon-freertos/demos/include/aws_clientcredential.h**. Scroll down to find:

    #define clientcredentialMQTT_BROKER_ENDPOINT ""

Insert the AWS IoT Core endpoint from your own account.

Then a few lines below you will find: 

    #define clientcredentialIOT_THING_NAME ""

Insert the thing name created earlier.

