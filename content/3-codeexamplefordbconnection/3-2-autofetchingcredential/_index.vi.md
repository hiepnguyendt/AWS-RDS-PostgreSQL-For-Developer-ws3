---
title : "Tự động tìm nạp thông tin xác thực và kết nối"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---

#### Triển khai example code

1. Để clone code từ GitHub, bạn có thể sử dụng lệnh sau:
  ```
  git clone https://github.com/hiepnguyendt/Auto-fetching-instance-credentialsand-connecting.git
  ```

![autofetching](/images/2.2/1.png)

2. Chỉnh sửa file **.env** với thông tin xác thực cơ sở dữ liệu của bạn
  ```
  nano .env

  ```
![autofetching](/images/2.2/2.png)

- **AWS_REGION**: region của bạn

![autofetching](/images/2.2/3.png)

3. Chạy code:
  ```
  npm start

  ```

![autofetching](/images/2.2/4.png)

Bây giờ, bạn đang kết nối với RDS PostgreSQL bằng cách Tự động tìm nạp thông tin xác thực instance từ AWS Secret Manager.

{{%notice note%}}
Nếu bạn gặp lỗi khi chạy mã. Bạn nên kiểm tra AWS_region trong AWS CLI
{{%/notice%}}




