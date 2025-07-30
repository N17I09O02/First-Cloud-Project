---
title : "Tạo S3 Notify by Lambda"
date: "2025-06-14"
weight : 3 
chapter : false
pre : " <b> 3.3. </b> "
---
1. Truy cập vào [giao diện quản trị của dịch vụ S3](https://console.aws.amazon.com/s3/home).

   + Click chọn **cf-templates-29w3zrvbs88r-us-east-1**.

![SNS](/images/3.connect/S3_notifi_Lambda_1.png)

2. Tại trang chi tiết.
   + Click chọn **Properties**.
   + Kéo xuống dưới phần **Event notifications** chọn **Create event notification**.

![SNS](/images/3.connect/S3_notifi_Lambda_2.png)

<!-- {{% notice note %}}
Bạn sẽ cần chờ khoảng 10 phút trước khi thực hiện bước tiếp theo. Thời gian này EC2 instance của chúng ta sẽ tự động đăng ký với Session Manager.
{{% /notice %}} -->

3. Tại trang **Create event notification**
   + Tại phần **Event name** điền **Notify-Upload-lambda**.
   + Tại phần **Subffix - optional** điền **.jpg**.
   + Click **Start Session**.
   + Ở **Object creation** chọn **Put**. 

![SNS](/images/3.connect/S3_notifi_Lambda_3.png)


4. Qua phần **Destination**.
   + Chọn **Lambda function**.
   + Chọn **Choose from your Lambda Functions**. 
   + Ở **Lambda function** chọn **NotifyS3Upload**. 
   + Cuối cùng chọn **Save changes**.

![SNS](/images/3.connect/S3_notifi_Lambda_4.png)


5. Đây là giao diện sau khi tạo xong.

![SNS](/images/3.connect/S3_notifi_Lambda_5.png)

6. Quay lại trang chi tiết chúng ta sẽ thử upload hình lên để xem có thông báo không. 

   + Chọn **Upload**.

![SNS](/images/3.connect/S3_notifi_Lambda_6.png)

7. Kéo hình từ máy vào đây.

{{% notice note %}}
Bạn cần up hình có đuôi là .jpg vì lúc nãy ta thiết lập chỉ thông báo khi hình có đuôi là .jpg
{{% /notice %}}

![SNS](/images/3.connect/S3_notifi_Lambda_7.png)

8. Sau khi up hình lên ta kéo xuống dưới chọn **Upload**.

![SNS](/images/3.connect/S3_notifi_Lambda_8.png)

9. Giao diện sau khi upload thành công.

![SNS](/images/3.connect/S3_notifi_Lambda_9.png)

10. Bạn sẽ nhận được một Email thông báo. 

![SNS](/images/3.connect/S3_notifi_Lambda_10.png)

