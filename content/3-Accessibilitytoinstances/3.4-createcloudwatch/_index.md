---
title : "Create CloudWatch Monitoring"
date: "2025-06-14"
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---

1. Go to the [CloudWatch service management console](https://console.aws.amazon.com/cloudwatch/home).  
   + Click **Alarms**.  
   + Click **All alarms**.  
   + Click **Create alarm**.

![SNS](/images/3.connect/CloudWatch_EC2_1.png)

2. On the **Specify metric and conditions** page:  
   + Click **Select metric**.

![SNS](/images/3.connect/CloudWatch_EC2_2.png)

<!-- {{% notice note %}}
You will need to wait about 10 minutes before proceeding to the next step. During this time, our EC2 instance will automatically register with Session Manager.
{{% /notice %}} -->

3. On the **Select metric** interface:  
   + Scroll down and select **EC2**.  
   + Choose **Per-Instance Metrics**.  
   + Find and select **CPUUtilization**.  
   + Click **Select metric**.

![SNS](/images/3.connect/CloudWatch_EC2_3.png)

4. In the **Threshold** section, enter **80**  
   + Click **Next**.

![SNS](/images/3.connect/CloudWatch_EC2_4.png)

5. In the **Notification** section, click **Add notification**.  
   + Under **Send a notification to…**, select **Notify-Alerts**.

![SNS](/images/3.connect/CloudWatch_EC2_5.png)

6. In the **Lambda action** section, click **Add Lambda action**.  
   + Under **Choose a function**, select **StopEC2OnHighCPU**.  
   + Click **Next**.

![SNS](/images/3.connect/CloudWatch_EC2_6.png)

7. On the **Add alarm details** page:  
   + In the **Add alarm details** section, enter a unique name.  
   + Click **Next**.

![SNS](/images/3.connect/CloudWatch_EC2_7.png)

8. Review the information and click **Create Alarm**.

![SNS](/images/3.connect/CloudWatch_EC2_8.png)

9. Interface after successful creation.

![SNS](/images/3.connect/CloudWatch_EC2_9.png)

<!-- {{% notice note %}}
Earlier, we established a connection to the public instance without opening SSH port 22, which enhances security by preventing attacks on the SSH port.  
One downside of the above approach is that we had to open outbound port 443 to the internet in the security group. Since this is a public instance, it might not be an issue, but if you want even more security, you can block outbound port 443 while still using Session Manager. We will go through this method in the private instance section below.
{{% /notice %}} -->
