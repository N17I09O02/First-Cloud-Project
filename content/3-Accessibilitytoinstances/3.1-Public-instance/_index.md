---
title : "Create SNS"
date: "2025-06-14"
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

1. Go to the [SNS service management console](https://console.aws.amazon.com/sns/v3/home).  
   + Click **Topics**.  
   + Click **Create topic**.

![SNS](/images/3.connect/SNS_1.png)

2. On the Create topic page:  
   + Select **Standard**.  
   + In the **Name** field, enter **Notify-Alerts**.

![SNS](/images/3.connect/SNS_2.png)

<!-- {{% notice note %}}
You will need to wait about 10 minutes before proceeding to the next step. During this time, our EC2 instance will automatically register with Session Manager.
{{% /notice %}} -->

3. Scroll down and click **Create topic**.

![SNS](/images/3.connect/SNS_3.png)

4. This is the interface after creation.  
   + Click **Create subscription**.

![SNS](/images/3.connect/SNS_4.png)

5. On the **Create subscription** page:  
   + In the **Protocol** field, select **Email**.  
   + In the **Endpoint** field, enter your email address.  
   + Then click **Create subscription**.

![SNS](/images/3.connect/SNS_5.png)

6. You will then receive a confirmation email.  
   + Click **Confirm subscription**.

![SNS](/images/3.connect/SNS_6.png)

7. You will then be redirected to the confirmed page.

![SNS](/images/3.connect/SNS_7.png)

8. Return to the SNS page and you will see a success notification.

![SNS](/images/3.connect/SNS_8.png)

<!-- {{% notice note %}}
Earlier, we established a connection to the public instance without opening SSH port 22, which enhances security by preventing attacks on the SSH port.  
One downside of the above approach is that we had to open outbound port 443 to the internet in the security group. Since this is a public instance, it might not be an issue, but if you want even more security, you can block outbound port 443 while still using Session Manager. We will go through this method in the private instance section below.
{{% /notice %}} -->
