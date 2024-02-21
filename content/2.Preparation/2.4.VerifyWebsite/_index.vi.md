---
title : "Kiểm tra website"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

### Vùng chính
1. Nhấn [CloudFormation Stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/events?stackId=arn%3Aaws%3Acloudformation%3Aus-west-1%3A170074558790%3Astack%2Fnetwork-stack%2F97f9d5d0-9f10-11ee-a02a-06401036bc1b&filteringText=&filteringStatus=active&viewNested=true) để chuyển hướng đến giao diện của vùng **N. Virginia (us-east-1)**.
2. Chọn stack **pilot-primary**.
3. Nhấn vào thanh chuyển hướng **Output**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.1verifywebsite.png?width=90pc)

4. Nhấn vào đường dẫn đầu ra **WebsiteURL** và mở trong một giao diện web mới.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.2verifywebsite.png?width=90pc)

5. Tại trang web, nhấn **Sign up** để tạo tài khoản.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.3verifywebsite.png?width=89pc)

6. Điền thông tin cần thiết để tạo tài khoản.
7. Sau đó, nhấn **Signup** để hoàn tất bước này.

{{%notice warning%}}
Hãy lưu trữ các thông tin mà bạn đã cung cấp trong bước này
{{%/notice%}}
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.4verifywebsite.png?width=90pc)

8. Nhấn **Log in**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.5verifywebsite.png?width=89pc)
9. Điền thông tin bạn đã cung cấp.
10. Sau đó, nhấn **Login**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.6verifywebsite.png?width=90pc)

11. Sau khi đăng nhập thành công, nhấn **Unicorn** mà bạn muốn. Sau đó nhấn **Add to cart** để thêm vào giỏ hàng của bạn.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.7verifywebsite.png?width=90pc)

12. Sau khi bạn thêm **Unicorn** vào giỏ hàng thành công, kiểm tra biểu tượng **Cart** để thấy số lượng đã được tăng lên.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.8verifywebsite.png?width=90pc)

13. Lặp lại bước 12 để thêm nhiều sản phẩm hơn vào giỏ hàng.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.9verifywebsite.png?width=90pc)

14. Sau khi hoàn tất các bước. Lưu lại số lượng sản phẩm trong giỏ hàng và khu vực của nó. Chúng ta sẽ kiểm tra lại chúng sau khi thực hiện nhân bản website đến khu vực thứ cấp.

{{%notice note%}}
Trong trường hợp này, số lượng trong giỏ hàng là **5** và khu vực là **us-east-1** (khu vực chính).
{{%/notice%}}
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.10verifywebsite.png?width=90pc)


### Vùng thứ cấp
Vùng thứ cấp của bạn phải là không khả dụng. Trong chiến lược khắc phục thảm họa Pilot Light, sẽ không có máy chủ .
1. Đi đến [CloudFormation Stacks]() trong vùng **N. California (us-west-1)**.
2. Chọn stank **pilot-secondary**.
3. Nhấn vào thanh chuyển hướng **Outputs**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.11verifywebsite.png?width=90pc)

4. Nhấn đường dẫn đầu ra WebsiteURL và mở trong trình duyệt web mới.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.12verifywebsite.png?width=90pc)

5. Bạn sẽ thấy lỗi trang 404.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.13verifywebsite.png?width=90pc)