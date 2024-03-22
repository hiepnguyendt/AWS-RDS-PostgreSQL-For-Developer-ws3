---
title : "Ví dụ về code dùng để kết nối cơ sở dữ liệu"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

Các bài thực hành trong phần này cung cấp các ví dụ triển khai để truy cập vào các phiên bản RDS PostgreSQL. Chúng có thể phục vụ như một tài liệu tham khảo cơ bản có thể được sử dụng để triển khai thực tế trong các ứng dụng.

1. [Simple database connection](3-1-sampledbconnect): Trong ví dụ đầu tiên, chúng ta tạo kết nối cơ sở dữ liệu đến RDS PostgreSQL instance. Các thuộc tính kết nối (DB endpoint, DB port, username và password) được tìm nạp từ các biến môi trường.
2. [Auto-fetching instance credentials and connecting](3-2-autofetchingcredential): Trong ví dụ thứ hai, chúng ta tạo kết nối đến RDS PostgreSQL instance sau khi tìm nạp thuộc tính kết nối bằng cách mô tả RDS instance và tìm nạp thông tin xác thực từ Secrets Manager bằng AWS SDK. AWS_REGION được tìm nạp từ biến môi trường AWS_REGION.
