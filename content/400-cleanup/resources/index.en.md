---
title : "Cleanup Resources"
weight : 1
---

You can also remove additional AWS resources if you will not need them again later. For Things, Ceertificates, and Policies the order of cleanup is important. 

- Certificates must be detached from Things before the Thing can be deleted.
- Certificates must be deactivated and Policies detached before the Certificate can be deleted.
- Policies must not be in use (attached) to other Certificates before they can be deleted.  

### Detach Certificate from Thing

Navigate to the IoT Core Service page and then select Manage -> Things from the left column. Select the thing to open the details page. Then select the Certificates tab and check the box next to the certificate. Now click the Detach button on the right.

![Detach Certificate](/static/detach-cert.png)

### Delete Thing

Navigate to the IoT Core Service page and then select Manage -> Things from the left column. Check the box next to the Thing you want to delete and the click the Delete button in the top-right area of the page.

![Delete Thing](/static/delete-thing.png)

### Deactivate Certificate

Navigate to the IoT Core Service page and then select Manage -> Security -> Certificates. Check the box next to the Certificate you want to deactivate. Then from the Actions dropdown list select Deactivate.

![Deactivate Cert](/static/deactivate-cert.png)

### Detach Policy from Certificate

Navigate to the IoT Core Service page and then select Manage -> Security -> Certificates. Select the certificate to open the details page. Then check the box next to the policy you want to detach and click the Detach policies button on the right.

![Detach Policy](/static/detach-policy.png)

## Delete Certificates

Now you can delete the Certificate. Navigate to the IoT Core Service page and then select Manage -> Security -> Certificates. Check the box next to the Certificate you want to delete. Then from the Actions dropdown list select Delete.

![Deactivate Cert](/static/deactivate-cert.png)
