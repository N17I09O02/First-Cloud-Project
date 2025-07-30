---
title : "Create Lambda"
date: "2025-06-14"
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---

1. Go to the [Lambda service management console](https://console.aws.amazon.com/lambda/home).  
   
   + Click **Create Function**.

![SNS](/images/3.connect/Lambda_1.png)

2. On the **Create function** page:  
   + In **Function name**, enter **StopEC2OnHighCPU**.  
   + In **Runtime**, select **Python 3.13**.  
   + In **Function role**, choose **Use an existing role**.  
   + In **Existing role**, select **LambdaStopEC2Role**.  
   + Click **Create Function**.

![SNS](/images/3.connect/Lambda_2.png)

<!-- {{% notice note %}}
You will need to wait about 10 minutes before proceeding to the next step. During this time, our EC2 instance will automatically register with Session Manager.
{{% /notice %}} -->

3. After creation, the function interface appears.  
   + Add the following code to the **Code source** section:

    ```
        import boto3

        def handler(event, context):
        ec2 = boto3.client('ec2')
        
        # Replace with your actual Instance ID
        instance_id = 'i-0a46358d5******'
        
        response = ec2.stop_instances(InstanceIds=[instance_id])
        print(f"✅ EC2 instance {instance_id} is being stopped. Response: {response}")
    ```

    + After adding the code, click **Deploy** or press **Ctrl + Shift + U**.

![SNS](/images/3.connect/Lambda_3.png)

4. Repeat from step 1:  
    + In **Function name**, enter **NotifyS3Upload**.  
    + In **Existing role**, select **Lambda_S3_Notify_Role**.  
    + Click **Create Function**.

![SNS](/images/3.connect/Lambda_4.png)

5. Similarly, add the following code to **Code source**:

    ```
    import boto3

    def lambda_handler(event, context):
        print("🧾 S3 Event Triggered:")
        print(event)

        python
        Sao chép
        Chỉnh sửa
        sns = boto3.client('sns')
        response = sns.publish(
            # Replace the ARN with your actual ARN from SNS -> ARN
            TopicArn='arn:aws:sns:us-east-1:958699963579:Notify-Alerts',
            Subject='🖼️ New image uploaded to S3!',
            Message=f'S3 Upload Event:\n{event}'
        )

        print("📤 SNS Sent:", response)
    ```
