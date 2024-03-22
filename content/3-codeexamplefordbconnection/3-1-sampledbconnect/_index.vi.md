---
title : "Kết nối cơ sở dữ liệu đơn giản"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

#### Triển khai simple code  

1. Để clone code từ GitHub, bạn có thể sử dụng lệnh sau:
  ```
  git clone https://github.com/hiepnguyendt/sample-database-connection.git
  ```

![simplecode](/images/2.1/1.png)

2. Chỉnh sửa file **.env** với thông tin xác thực cơ sở dữ liệu của bạn
  ```
  nano .env

  ```
![simplecode](/images/2.2/4.png)

- **DB_USER**: 'your username'  
- **DB_PASS**: 'your password'
- **DB_HOST**: 'endpoint your RDS PostgreSQL'
- **DB_PORT**: '5432'

![simplecode](/images/2.1/3.png)

3. Chạy code:
  ```
  npm start
  ```

![simplecode](/images/2.1/2.png)

Bây giờ, bạn đang kết nối với RDS PostgreSQL với:
- **User**: masteruser
- **Database**: pglab
- **Port**: 5432