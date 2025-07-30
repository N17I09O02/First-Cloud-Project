---
title : "Tạo Lambda"
date: "2025-06-14"
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
1. Truy cập vào [giao diện quản trị của dịch vụ Lambda](https://console.aws.amazon.com/lambda/home).
   
   + Click chọn **Create Function**.

![SNS](/images/3.connect/Lambda_1.png)

2. Tại trang **Create function**.
   + Tại mục **Function name** điền **StopEC2OnHighCPU**.
   + Tại mục **Runtime** chọn **Python 3.13**.
   + Ở **Function role** chọn **Use an exsting role**.
   + Ở **Exsting role** chọn **LambdaStopEC2Role**.
   + Chọn **Create Function**.

![SNS](/images/3.connect/Lambda_2.png)

<!-- {{% notice note %}}
Bạn sẽ cần chờ khoảng 10 phút trước khi thực hiện bước tiếp theo. Thời gian này EC2 instance của chúng ta sẽ tự động đăng ký với Session Manager.
{{% /notice %}} -->

3. Giao diện sau khi tạo xong.

   + Thêm đoạn code sau vào phần **Code source**.

   ```
    import boto3

    def handler(event, context):
      ec2 = boto3.client('ec2')
      
      # Thay bằng Instance ID thật của bạn
      instance_id = 'i-0a46358d5******'
      
      response = ec2.stop_instances(InstanceIds=[instance_id])
      print(f"✅ EC2 instance {instance_id} is being stopped. Response: {response}")
    ```

   + Sau khi thêm thì chọn **Deploy** hoặc nhấn tổ hợp phím **Ctrl + Shift + U**.

![SNS](/images/3.connect/Lambda_3.png)


4. Làm lại từ bước 1.

   + Ở phần **Function name** điền **NotifyS3Upload**.
   + Ở **Exsting role** chọn **Lambda_S3_Notify_Role**.
   + Và chọn **Create Function**.

![SNS](/images/3.connect/Lambda_4.png)


5. Tương tự như trên ta sẽ thêm đoạn code sau vào **Code source**.

   ```
   import boto3

   def lambda_handler(event, context):
      print("🧾 S3 Event Triggered:")
      print(event)

      sns = boto3.client('sns')
      response = sns.publish(
         # Thay ARN bằng đường dẫn ARN của bạn lấy trong SNS -> ARN
         TopicArn='arn:aws:sns:us-east-1:958699963579:Notify-Alerts',
         Subject='🖼️ S3 có ảnh mới!',
         Message=f'S3 Upload Event:\n{event}'
      )

      print("📤 SNS Sent:", response)
   ```

![SNS](/images/3.connect/Lambda_5.png)

6. Bạn có thể truy cập vào [Dịch vụ Lambda](https://console.aws.amazon.com/sns/v3/home) để lấy được ARN. 

![SNS](/images/3.connect/Lambda_6.png)

7. Sau khi bạn **Deploy** xong ta chọn **Configuration**.

   + Kéo xuống dưới chọn vào chỉ mục **Permissions**.
   + Kéo xuống dưới chọn **Add permissions**

![SNS](/images/3.connect/Lambda_7.1.png)

8. Tại giao diện **Add permissions**

   + Chọn **AWS Service**.
   + Tại **Serive chọn S3**.
   + Ở **Statement ID** điền **AllowS3Invoke**.
   + Ở **Principal** điền địa chỉ ARN của SNS hồi nãy.
   + Ở phần **Action** chọn **lambda:InvokeFunction**.
   + Cuối cùng chọn **Save**.

![SNS](/images/3.connect/Lambda_7.png)

9. Giao diện khi tạo xong.

![SNS](/images/3.connect/Lambda_8.png)


