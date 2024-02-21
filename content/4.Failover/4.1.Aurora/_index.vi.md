---
title : "Aurora"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---
[Amazon Aurora Global Database](https://aws.amazon.com/vi/rds/aurora/global-database/) được thiết kế cho các ứng dụng phân phối toàn cầu, cho phép một CSDL Amazon Aurora đơn lẻ trải khắp các khu vực AWS. Nó nhân bản dữ liệu của bạn mà không ảnh hưởng đến hiệu năng của CSDL, cho phép đọc cục bộ nhanh chóng với độ trễ thấp trong từng khu vực, và cung cấp khả năng khắc phục thảm họa sau khi ngừng hoạt động trên toàn khu vực. Trong các tình huống khắc phục thảm họa, bạn có thể nâng cấp một khu vực thứ cấp để có thể đảm nhiệm toàn bộ trách nhiệm đọc-ghi trong vòng chưa đầy một phút. 

Với một CSDL toàn cầu Aurora, có 2 hướng khác nhau để phục hồi tùy theo tình huống.

**Failover** – Sử dụng phương thức này để phục hồi sau sự cố ngừng hoạt động. Với phương pháp này, bạn thực hiện chuyển đổi dự phòng giữa các khu vực sang một trong các cụm CSDL thứ cấp trong CSDL toàn cầu Aurora. PRO cho phương pháp này thường là giả trị khác 0 được đo bằng giây. Lượng dữ liệu mất đi tùy thuộc vào độ trễ của việc nhân bản CSDL toàn cầu Aurora tài thời điểm chuyển đổi dự phòng.

**Switchover** – Thao tác này trước đó được gọi là "Chuyển đổi dự phòng được lên kế hoạch quản lí". Sử dụng phương pháp này cho các kịch bản được kiểm soát, chẳng hạn như bảo trì vận hành và các quy trình vận hành theo kế hoạch khác. Bời vì chức năng này đồng bộ cụm CSDL thứ cấp với CSDL chính trước khi có sự thay đổi nào, RPO là 0 (không có dữ liệu bị mất).

**Switchover**, được thể hiện trong bài thực hành **Warm Standby**.

Với bài thực hành này chúng ta sẽ thực hiện một **Failover**.

1. Đi đến [RDS](https://us-west-1.console.aws.amazon.com/rds/home?region=us-west-1#databases:) trong vùng **N. California (us-west-1)**.
2. Xem xét CSDL toàn cầu **pilot-global**. Chú ý bạn có **pilot-primary** là cụm chính trong **us-east-1** với **Writer instance** and **pilot-secondary** và cụm thứ cấp trong vùng **us-west-1** với **Reader instance**.
![Failover Aurora](../../../images/4.failover/4.1.aurora/4.1.1aurora.png?width=90pc)

3. Chọn cụm **pilot-global**.
4. Nhấn **Actions**.
5. Chọn **Switch over or fail over global database** dưới **Actions**.
![Failover Aurora](../../../images/4.failover/4.1.aurora/4.1.2aurora.png?width=90pc)

6. Chọn **Failover (allow data loss)**.
7. Tại mục **New primary cluster**, chọn **pilot-secondary**.
8. Nhập ```confirm```.
9. Sau đó, nhấn **Confirm**.
![Failover Aurora](../../../images/4.failover/4.1.aurora/4.1.3aurora.png?width=90pc)

10. Sẽ mất khoảng vài phút để nâng cấp CSDL thứ cấp thành CSDL chính.
![Failover Aurora](../../../images/4.failover/4.1.aurora/4.1.4aurora.png?width=90pc)

11. Sau khi quá trình chuyển đổi dự phòng hoàn tất, chú ý sự thay đổi. Cụm **Primary cluster** hiện giờ trong vùng **us-west-1** với **Writer instance** và cụm **Secondary Cluster** hiện giờ trong vùng **us-east-1** với **Reader instance**. 
![Failover Aurora](../../../images/4.failover/4.1.aurora/4.1.5aurora.png?width=90pc)
