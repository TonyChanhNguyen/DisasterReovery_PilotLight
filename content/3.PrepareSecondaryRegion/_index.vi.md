---
title : "Chuẩn bị vùng thứ cấp"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

Trong bước này, chúng ta sẽ thực hiện tạo một EC2 AMI tại vùng chính, sau đó sao chép nó đến vùng thứ cấp để khởi chạy máy chủ EC2 trên đó.
### Tạo EC2 Amazon Machine Image (AMI)
1. Đi đến [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Instances:v=3;$case=tags:true%5C,client:false;$regex=tags:false%5C,client:false) tại vùng chính **N. Virginia (us-east-1)**.

2. Chọn máy chủ tên **pilot-primary**.
3. Nhấn **Action**.
4. Nhấn **Images and Templates** ở dưới **Action**.
5. Sau đó, nhấn **Create image**.
![Prepare secondary region](/../images/3.preparesecondaryregion/3.1preparesecondaryregion.png?width=90pc)

6. Nhập ```pilotAMI``` tại **Image name**.
7. Sau đó, nhấn **Create image**.
![Prepare secondary region](/../../images/3.preparesecondaryregion/3.2preparesecondaryregion.png?width=90pc)

### Sao chép EC2 Amazon Machine Image (AMI)
1. Nhấn [AMIs](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Images:visibility=owned-by-me) để chuyển hướng đến giao diện.
2. Chọn AMI **pilotAMI**.
3. Nhấn **Action**.
4. Nhấn **Copy AMI** dưới **Action**.
![Prepare secondary region](/../../images/3.preparesecondaryregion/3.3preparesecondaryregion.png?width=90pc)

5. Tại trang **Copy AMI**, chọn vùng thứ cấp **US West (N. California)** tại **Destination Region**.
6. Sau đó, nhấn **Copy AMI**.
![Prepare secondary region](/../../images/3.preparesecondaryregion/3.4preparesecondaryregion.png?width=90pc)

7. Đi đến [AMIs](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Images:visibility=owned-by-me) tại vùng thứ cấp **N. California (us-west-1)**, bạn sẽ thấy có một AMI với trạng thái là **Pending**.
![Prepare secondary region](/../../images/3.preparesecondaryregion/3.5preparesecondaryregion.png?width=90pc)

8. Sẽ mất khoảng 5 phút để một AMI được sao chép thành công.
![Prepare secondary region](/../../images/3.preparesecondaryregion/3.6preparesecondaryregion.png?width=90pc)



