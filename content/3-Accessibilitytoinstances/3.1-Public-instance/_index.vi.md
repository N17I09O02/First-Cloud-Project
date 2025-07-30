---
title : "Tạo SNS"
date: "2025-06-14"
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---
1. Truy cập vào [giao diện quản trị của dịch vụ SNS](https://console.aws.amazon.com/sns/v3/home).
   + Click chọn **Topics**.
   + Chọn **Create topic**.

![SNS](/images/3.connect/SNS_1.png)

2. Tại trang Create topic.
   + Click chọn **Standard**.
   + Tại ô **Name** điền **Notify-Alerts**.

![SNS](/images/3.connect/SNS_2.png)

<!-- {{% notice note %}}
Bạn sẽ cần chờ khoảng 10 phút trước khi thực hiện bước tiếp theo. Thời gian này EC2 instance của chúng ta sẽ tự động đăng ký với Session Manager.
{{% /notice %}} -->

3. Kéo xuống dưới chọn **Create topic**.

![SNS](/images/3.connect/SNS_3.png)


4. Đây là giao diện sau khi tạo xong.

   + Chọn **Create subscription**.

![SNS](/images/3.connect/SNS_4.png)


5. Tại giao diện **Create subscription**.

   + Tại Ô **Protocol** chọn **Email** .
   + Tại Ô **Endpoint** điền Email của bạn.  
   + Sau đó **Create subscription**. 

![SNS](/images/3.connect/SNS_5.png)

6. Sau đó bạn sẽ bạn sẽ nhận mail xác nhận. 

   + Chọn **Confirm subscription**

![SNS](/images/3.connect/SNS_6.png)

7. Sau đó bạn sẽ được đưa đến trang đã xác nhận.

![SNS](/images/3.connect/SNS_7.png)

8. Sau đó quay lại trang SNS bạn sẽ thấy thông báo thành công.

![SNS](/images/3.connect/SNS_8.png)

<!-- {{% notice note %}}
 Ở trên, chúng ta đã tạo  kết nối vào public instance mà không cần mở cổng SSH 22, giúp cho việc bảo mật tốt hơn, tránh mọi sự tấn công tới cổng SSH.\
Một nhược điểm của cách làm trên là ta phải mở Security Group outbound ở cổng 443 ra ngoài internet. Vì là public instance nên có thể sẽ không vấn đề gì nhưng nếu bạn muốn bảo mật hơn nữa, bạn có thể khoá cổng 443 ra ngoài internet mà vẫn sử dụng được Session Manager. Chúng ta sẽ đi qua cách làm này ở phần private instance dưới đây.
 {{% /notice %}} -->

