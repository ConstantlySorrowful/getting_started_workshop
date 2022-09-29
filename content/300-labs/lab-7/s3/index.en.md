---
title : "Lab 7: Working With STM32U5 in Keil Studio Cloud (KSC) (Step 3)"
weight : 3
---

## Create a new certificate and attach a policy

1. Now click th AWS icon on the left side of the IDE window to open the **AWS Toolkit**.

![aws](/static/aws-icon.png)

2. Now open the IoT Section and then click on the **+** symbol next to **Certificates** and then select the new **local** folder you created. Then click **Save certificate here**.

![aws toolkit cert](/static/aws-tookit-cert.png)

3. Now attach a ploicy and activate the new certificate.

![attach policy](/static/cert-attach-policy.png)

4. Create a new thing. Select the **+** symbol next the **Things**. A prompt will appear to provide a name for your new thing.

![new thing](/static/new-thing.png)

5. Now attach the certificate created earlier to your new thing.

![thing attach cert](/static/thing-attach-cert.png)
