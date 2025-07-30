+++
title = "Dọn dẹp tài nguyên"
date = "2025-06-14"
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

Chúng ta sẽ tiến hành các bước sau để xóa các tài nguyên chúng ta đã tạo trong bài thực hành này.

1. Truy cập [giao diện quản trị dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home)
  + Click **Instances**.
  + Click chọn cả 2 instance **Public Linux Instance** và **Private Windows Instance**. 
  + Click **Instance state**.
  + Click **Terminate instance**, sau đó click **Terminate** để xác nhận.

![Clean](/images/Delete_EC2_1.png)

2. Truy cập [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iamv2/home#/home)
  + Click **Roles**.
  + Tại ô tìm kiếm , điền **Lambda_S3_Notify_Role**.
  + Click chọn **Lambda_S3_Notify_Role**.
  + Click **Delete**, sau đó điền tên role **Lambda_S3_Notify_Role** và click **Delete** để xóa role.
  + Làm tương tự với **LambdaStopEC2Role**
  
![Clean](/images/Delete_S3_1.png)

4. Truy cập [giao diện quản trị dịch vụ S3](https://s3.console.aws.amazon.com/s3/home)
  + Click chọn S3 bucket chúng ta đã tạo cho bài thực hành.
  + Click **Empty**.
  + Điền **permanently delete**, sau đó click **Empty** để tiến hành xóa object trong bucket.
  + Click **Exit**.
  + Để đảm bảo xóa sạch bạn có thể tham https://000057.awsstudygroup.com/11-cleanup/
  ![Clean](/images/Delete_S3_2.png)


5. Truy cập [giao diện quản trị dịch vụ RDS](https://s3.console.aws.amazon.com/s3/home)

  + Chọn **database-1**.
  + Chọn **Actions**.
  + Chọn **Delete**.

  ![Clean](/images/Delete_RDS_1.png)

  + Bỏ tick **Create final snapshot** và **Retain automated backups**.
  + Chọn **I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available**.
  + Điền **delete me** vào **To confirm deletion, type delete me into the field**.

  ![Clean](/images/Delete_RDS_2.png)

  6. Truy cập [giao diện quản trị dịch vụ VPC](https://s3.console.aws.amazon.com/vpcconsole/home)
  + Bạn có thể tham khỏa cách xóa ở bài lab này https://000003.awsstudygroup.com/6-cleanup/
  + Xóa Subnet
  ![Clean](/images/Delete_VPC_1.png)
  ![Clean](/images/Delete_VPC_1.1.png)

  + Xóa SecurityGroup
  ![Clean](/images/Delete_VPC_2.png)
  ![Clean](/images/Delete_VPC_2.2.png)

  + Xóa router
  ![Clean](/images/Delete_VPC_3.png)

  + Xóa Your VPC
  ![Clean](/images/Delete_VPC_4.png)
  ![Clean](/images/Delete_VPC_4.1.png)

7. Truy cập [giao diện quản trị dịch vụ SNS](https://s3.console.aws.amazon.com/sns/v3/home)

  ![Clean](/images/Delete_SNS_1.png)

  ![Clean](/images/Delete_SNS_2.png)

8. Truy cập [giao diện quản trị dịch vụ Lambda](https://s3.console.aws.amazon.com/lambda/home)

  ![Clean](/images/Delete_Lambda_1.png)

  ![Clean](/images/Delete_Lambda_2.png)

9. Truy cập [giao diện quản trị dịch vụ CloudWatch](https://s3.console.aws.amazon.com/cloudwatch/home)

  ![Clean](/images/Delete_CW_1.png)

  ![Clean](/images/Delete_CW_2.png)
