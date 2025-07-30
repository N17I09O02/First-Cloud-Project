---
title : "Create S3 Notify by Lambda"
date: "2025-06-14"
weight : 3 
chapter : false
pre : " <b> 3.3. </b> "
---

1. Go to the [S3 service management console](https://console.aws.amazon.com/s3/home).  
   + Click on **cf-templates-29w3zrvbs88r-us-east-1**.

![SNS](/images/3.connect/S3_notifi_Lambda_1.png)

2. On the details page:  
   + Click **Properties**.  
   + Scroll down to the **Event notifications** section and click **Create event notification**.

![SNS](/images/3.connect/S3_notifi_Lambda_2.png)

<!-- {{% notice note %}}
You will need to wait about 10 minutes before proceeding to the next step. During this time, our EC2 instance will automatically register with Session Manager.
{{% /notice %}} -->

3. On the **Create event notification** page:  
   + In the **Event name** field, enter **Notify-Upload-lambda**.  
   + In the **Suffix - optional** field, enter **.jpg**.  
   + Click **Start Session**.  
   + Under **Object creation**, select **Put**.

![SNS](/images/3.connect/S3_notifi_Lambda_3.png)

4. In the **Destination** section:  
   + Choose **Lambda function**.  
   + Select **Choose from your Lambda Functions**.  
   + Under **Lambda function**, select **NotifyS3Upload**.  
   + Finally, click **Save changes**.

![SNS](/images/3.connect/S3_notifi_Lambda_4.png)

5. This is the interface after creation.

![SNS](/images/3.connect/S3_notifi_Lambda_5.png)

6. Go back to the details page to try uploading an image to see if a notification is received.  
   + Click **Upload**.

![SNS](/images/3.connect/S3_notifi_Lambda_6.png)

7. Drag an image from your computer into the upload area.

{{% notice note %}}
You need to upload an image with the `.jpg` extension because earlier we configured it to notify only for `.jpg` files.
{{% /notice %}}

![SNS](/images/3.connect/S3_notifi_Lambda_7.png)

8. After adding the image, scroll down and click **Upload**.

![SNS](/images/3.connect/S3_notifi_Lambda_8.png)

9. Interface after successful upload.

![SNS](/images/3.connect/S3_notifi_Lambda_9.png)

10. You will receive a notification email.

![SNS](/images/3.connect/S3_notifi_Lambda_10.png)
