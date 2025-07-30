---
title : "Tạo CloudWatch giám sát"
date: "2025-06-14"
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---
1. Truy cập vào [giao diện quản trị của dịch vụ Cloudwatch](https://console.aws.amazon.com/cloudwatch/home).
   + Click chọn **Alarms**.
   + Click **All alarms**.
   + Click **Create alarm**.

![SNS](/images/3.connect/CloudWatch_EC2_1.png)

2. Tại trang Specify metric and conditions.

   + Click chọn **Select metric**.

![SNS](/images/3.connect/CloudWatch_EC2_2.png)

<!-- {{% notice note %}}
Bạn sẽ cần chờ khoảng 10 phút trước khi thực hiện bước tiếp theo. Thời gian này EC2 instance của chúng ta sẽ tự động đăng ký với Session Manager.
{{% /notice %}} -->

3. Tại giao diện Select metric
   + Kéo xuống chọn **EC2**.
   + Chọn **Per-Instance Metrics**.
   + Tìm và chọn **CPUUtilization**.
   + Chọn **Select metric**.

![SNS](/images/3.connect/CloudWatch_EC2_3.png)


4. Ở phần **than…** ta điền **80**

   + Chọn **Next**.

![SNS](/images/3.connect/CloudWatch_EC2_4.png)


5. Ở phần **Notification** chọn **Add notification**.

   + Tại phần **Send a notification to…** chọn **Notify-Alerts**.

![SNS](/images/3.connect/CloudWatch_EC2_5.png)

6. ở phần **Lambda action** chọn **Add Lambda action**. 

   + Tại phần **Choose a function** chọn **StopEC2OnHighCPU**.
   + Chọn *Next*.

![SNS](/images/3.connect/CloudWatch_EC2_6.png)

7. Tại trang **Add alarm details**.

   + Tại phần **Add alarm details** điền tên bạn muốn lưu ý tên phải là duy nhất.
   + Chọn **Next**.

![SNS](/images/3.connect/CloudWatch_EC2_7.png)

8. Kiểm tra lại thông tin sau đó chọn **Create Alarm**.

![SNS](/images/3.connect/CloudWatch_EC2_8.png)

9. Giao diện sau khi tạo xong.

![SNS](/images/3.connect/CloudWatch_EC2_9.png)

<!-- {{% notice note %}}
 Ở trên, chúng ta đã tạo  kết nối vào public instance mà không cần mở cổng SSH 22, giúp cho việc bảo mật tốt hơn, tránh mọi sự tấn công tới cổng SSH.\
Một nhược điểm của cách làm trên là ta phải mở Security Group outbound ở cổng 443 ra ngoài internet. Vì là public instance nên có thể sẽ không vấn đề gì nhưng nếu bạn muốn bảo mật hơn nữa, bạn có thể khoá cổng 443 ra ngoài internet mà vẫn sử dụng được Session Manager. Chúng ta sẽ đi qua cách làm này ở phần private instance dưới đây.
 {{% /notice %}} -->


