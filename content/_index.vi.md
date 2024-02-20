---
title : "Pilot Light"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Pilot Light
Trong bài thực hành này, bạn sẽ trải qua chiến lược khắc phục thảm họa Pilot Light. Chiến lược khắc phục thảm họa Pilot Light có thời điểm khắc phục  /  Thời gian phục hồi (**Recovery Point Objective(RPO) / Recovery Time Objective (RTO)**) trong vòng 10 phút. Đối với khu vực thứ cấp của chiến lược Pilot Light, dữ liệu sẽ hoạt động và cơ sở hạ tầng cốt lõi sẽ được cung cấp, nhưng các dịch vụ sẽ không hoạt động hoặc không có.

Các ứng dụng hiện đang được triển khai tại khu vực chính N. Virginia (us-east-1). N. California (us-west-1) sẽ là khu vực thứ cấp của bạn.

Ứng dụng mẫu của bạn là **Unishop**. Nó là một ứng dụng Spring Boot Java được triển khai trên một máy chủ Amazon Elastic Compute Cloud (EC2) sử dụng một mạng con công cộng. Vùng chứa dữ liệu của bạn là một CSDL Amazon Aurora  MySQL với giao diện người dùng được viết bằng bootstrap và được lưu trữ trên Amazon Simple Storage Service (S3).

Bài thực hành này tận dụng ưu điểm của Amazon Machine Images (AMI) mà bạn sẽ sử dụng để khởi tạo máy chủ Amazon EC2 của bạn và Amazon Aurora Global Database để nhân bản dữ liệu Amazon Aurora MySQL của bạn đến khu vực thứ cấp.

CloudFormation sẽ được sử dụng để cấu hình cơ sở hạ tầng và triển khai ứng dụng. Cung cấp cơ sở hạ tầng của bạn với các phương thức cơ sở hạ tầng bằng code (IaC) là phương pháp tổt nhất. CloudFormation là một cách đơn giản để tăng tốc việc cung cấp dịch vụ đám mây với cơ sở hạ tầng bằng code


{{%notice info%}}
Bởi vì bài thực hành này chỉ có một máy chủ EC2 được triển khai chỉ trong một vùng sẵn sàng (Availability Zone), kiến trúc này không đáp ứng được của phương pháp tốt nhất Well Architected Framework cho việc chạy các ứng dụng trên môi trường sản phẩm có tính sẵn sàng cao nhưng phù hợp với bài thực hành này.
{{%/notice%}}


![Pilot Light](/images/pilotlight.png?width=60pc)