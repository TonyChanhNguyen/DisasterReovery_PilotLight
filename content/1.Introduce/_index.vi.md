---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
### Giới thiệu
Trong bài thực hành này, bạn sẽ trải qua chiến lược khắc phục thảm họa Pilot Light. Chiến lược khắc phục thảm họa Pilot Light có thời điểm khắc phục  /  Thời gian phục hồi (**Recovery Point Objective(RPO) / Recovery Time Objective (RTO)**) trong vòng 10 phút. Đối với khu vực thứ cấp của chiến lược Pilot Light, dữ liệu sẽ hoạt động và cơ sở hạ tầng cốt lõi sẽ được cung cấp, nhưng các dịch vụ sẽ không hoạt động hoặc không có.

Các ứng dụng hiện đang được triển khai tại khu vực chính N. Virginia (us-east-1). N. California (us-west-1) sẽ là khu vực thứ cấp của bạn.

Ứng dụng mẫu của bạn là **Unishop**. Nó là một ứng dụng Spring Boot Java được triển khai trên một máy chủ Amazon Elastic Compute Cloud (EC2) sử dụng một mạng con công cộng. Vùng chứa dữ liệu của bạn là một CSDL Amazon Aurora  MySQL với giao diện người dùng được viết bằng bootstrap và được lưu trữ trên Amazon Simple Storage Service (S3).

Bài thực hành này tận dụng ưu điểm của Amazon Machine Images (AMI) mà bạn sẽ sử dụng để khởi tạo máy chủ Amazon EC2 của bạn và Amazon Aurora Global Database để nhân bản dữ liệu Amazon Aurora MySQL của bạn đến khu vực thứ cấp.

CloudFormation sẽ được sử dụng để cấu hình cơ sở hạ tầng và triển khai ứng dụng. Cung cấp cơ sở hạ tầng của bạn với các phương thức cơ sở hạ tầng bằng code (IaC) là phương pháp tổt nhất. CloudFormation là một cách đơn giản để tăng tốc việc cung cấp dịch vụ đám mây với cơ sở hạ tầng bằng code


{{%notice info%}}
Bởi vì bài thực hành này chỉ có một máy chủ EC2 được triển khai chỉ trong một vùng sẵn sàng (Availability Zone), kiến trúc này không đáp ứng được của phương pháp tốt nhất Well Architected Framework cho việc chạy các ứng dụng trên môi trường sản phẩm có tính sẵn sàng cao nhưng phù hợp với bài thực hành này.
{{%/notice%}}

![Pilot Light](../images/pilotlight.png?width=60pc)

### Nội dung

1. [Giới thiệu](../1.introduce/)
2. [Các bước chuẩn bị](../2.preparation/)
    - 2.1 [Truy cập S3](../2.preparation/2.1.s3access/)
    - 2.2 [Vùng chính](../2.preparation/2.2.primaryregion/)
    - 2.3 [Vùng thứ cấp](../2.preparation/2.3.secondaryregion/)
    - 2.4 [Kiểm tra website](../2.preparation/2.4.verifywebsite/)
3. [Chuẩn bị vùng thứ cấp](../3.preparesecondaryregion/)
4. [Chế độ dự phòng](../4.failover/)
    - 4.1 [Aurora](../4.failover/4.1.aurora/)
    - 4.2 [EC2](../4.failover/4.2.ec2/)
    - 4.3 [Kiểm tra chế độ dự phòng](../4.failover/4.3.verifyfailover/)
5. [Dọn dẹp tài nguyên](../5.cleanupresources/)

