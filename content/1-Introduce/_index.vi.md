---
title : "Giới thiệu"
date: "2025-06-14"
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
<!-- **Session Manager** là một chức năng nằm trong dịch vụ System Manager của AWS, Session Manager cung cấp khả năng quản lý các máy chủ một cách an toàn mà **không cần mở port SSH, không cần Bastion Host hoặc quản lý SSH key**. 
Session Manager cũng giúp dễ dàng tuân thủ các chính sách của công ty yêu cầu quyền truy cập có kiểm soát, đảm bảo việc bảo mật nghiêm ngặt và ghi log truy việc truy cập trong khi vẫn cung cấp cho người dùng cuối quyền truy cập đa nền tảng.

Với việc sử dụng Session Manager, bạn sẽ có được những ưu điểm sau:

- Không cần phải mở cổng 22 cho giao thức SSH.
- Có thể cấu hình để kết nối không cần đi ra ngoài internet.
- Không cần quản lý private key của server để kết nối SSH.
- Quản lý tập trung được user bằng việc sử dụng AWS IAM.
- Truy cập tới server một cách dễ dàng và đơn giản bằng một cú click chuột.
- Thời gian truy cập nhanh chóng hơn các phương thức truyền thống như SSH.
- Hỗ trợ nhiều hệ điều hành khác nhau như Linux, Windows, MacOS.
- Log lại được các phiên kết nối và các câu lệnh đã thực thi trong lúc kết nối tới server.

Với những ưu điểm trên, bạn có thể sử dụng Session Manager thay vì sử dụng kỹ thuật Bastion host giúp chúng ta tiết kiệm được thời gian và chi phí khi quản lý server Bastion. -->

Hệ thống được triển khai dựa trên nền tảng dịch vụ đám mây AWS nhằm đảm bảo hiệu suất, bảo mật và khả năng mở rộng cho ứng dụng web.

Kiến trúc sử dụng các dịch vụ chính của AWS như EC2, RDS, S3, IAM, VPC, CloudWatch, Lambda và SNS, nhằm mục tiêu triển khai một hệ thống hoàn chỉnh từ xử lý đến giám sát, phân quyền và cảnh báo tự động.

Các thành phần chính của hệ thống:
 - EC2: Dùng để chạy dự án chính (ứng dụng web hoặc backend API) với khả năng tùy chỉnh linh hoạt về cấu hình máy chủ và mở rộng khi cần thiết.

 - RDS: Cung cấp cơ sở dữ liệu quản lý tập trung (ví dụ: MySQL, PostgreSQL) và được đặt trong VPC riêng biệt nhằm tăng cường bảo mật và tránh truy cập trái phép từ internet.

 - S3: Dùng để lưu trữ hình ảnh, tài liệu tĩnh hoặc các nội dung media từ hệ thống với khả năng mở rộng không giới hạn và chi phí thấp.

 - IAM: Quản lý phân quyền truy cập của người dùng (Admin, Dev...) theo đúng nguyên tắc tối thiểu quyền (least privilege), đảm bảo ai làm gì được trong hệ thống.

 - CloudWatch: Theo dõi và giám sát hiệu suất của hệ thống, bao gồm tài nguyên EC2, RDS và Lambda. Ghi log, cảnh báo khi có bất thường như CPU sử dụng cao, lỗi kết nối, v.v.

 - Lambda: Chạy các hàm tự động – ví dụ như gửi thông báo khi CPU EC2 vượt ngưỡng hoặc khi có sự kiện đặc biệt xảy ra trong hệ thống.

 - SNS: Kết hợp cùng Lambda để gửi email cảnh báo đến quản trị viên khi xảy ra sự cố (như quá tải CPU hoặc lỗi ứng dụng).

 - VPC: Cấu hình mạng riêng ảo (Virtual Private Cloud) đảm bảo hệ thống hoạt động cách ly, an toàn, và kiểm soát kết nối mạng tốt hơn.

Ưu điểm của mô hình:
 - Tự động hóa cảnh báo và giám sát thông minh, giúp phát hiện sự cố sớm.

 - Phân quyền rõ ràng giữa Dev và Admin nhờ IAM.

 - Bảo mật cao, không mở truy cập trực tiếp vào RDS từ internet.

 - Lưu trữ linh hoạt, chi phí thấp qua S3.

 - Dễ mở rộng và quản lý hiệu quả thông qua các dịch vụ tích hợp sẵn trên AWS.

Với kiến trúc này, hệ thống không chỉ đảm bảo tính sẵn sàng cao mà còn tiết kiệm thời gian vận hành và chi phí quản lý, rất phù hợp với các dự án thực tế trong môi trường doanh nghiệp hiện đại.