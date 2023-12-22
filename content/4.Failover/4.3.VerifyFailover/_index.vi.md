---
title : "Kiểm tra chế độ dự phòng"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 4.3 </b> "
---


1. Đi đến [CloudFormation Stacks](https://us-west-1.console.aws.amazon.com/cloudformation/home?region=us-west-1#/stacks/?filteringText=&filteringStatus=active&viewNested=true) trong vùng **N. California (us-west-1)**.
2. Nhấn vào stack tên **pilot-secondary**.

![Verify Failover](./images/4.failover/4.3.verifyfailover/4.3.1verifyfailover.png?width=90pc)

3. Nhấn thanh chuyển hướng **Outputs**.
![Verify Failover](./images/4.failover/4.3.verifyfailover/4.3.2verifyfailover.png?width=90pc)

4. Nhấn đường dẫn **WebsiteURL**.
![Verify Failover](./images/4.failover/4.3.verifyfailover/4.3.3verifyfailover.png?width=90pc)

5. Website của bạn sẽ xuất hiện như thế này.
![Verify Failover](./images/4.failover/4.3.verifyfailover/4.3.4verifyfailover.png?width=90pc)

6. Bây giờ chúng ta sẽ đăng nhập vào website để thấy kết quả. Các thông tin cần thiết để đăng nhập được tạo tại [2.4 Verify website](../../2.preparation/2.4.verifywebsite/).

7. Sau khi đăng nhập thành công, bạn có thể thấy tại giỏ hàng vẫn giữ số lượng đã lưu ở vùng chính. Và vùng hiện tại là **us-west-1**.

![Verify Failover](./images/4.failover/4.3.verifyfailover/4.3.5verifyfailover.png?width=90pc)


#### Chúc mừng, ứng dụng của bạn đã hoàn tất chuyển đổi dự phòng đến vùng thứ cấp **N. California (us-west-1)** từ vùng chính **N. Virginia (us-east-1)** thành công.