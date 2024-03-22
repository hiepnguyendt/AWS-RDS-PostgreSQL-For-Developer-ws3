---
title : "AWS Secret Manager"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2.</b> "
---

#### Tạo AWS Secrets Manager secret

**Secrets Manager** cho phép bạn thay thế thông tin xác thực được mã hóa cứng trong mã của mình, bao gồm cả mật khẩu, bằng lệnh gọi API tới Trình quản lý bí mật để truy xuất bí mật theo chương trình. Điều này giúp đảm bảo bí mật không thể bị xâm phạm bởi ai đó đang kiểm tra mã của bạn vì bí mật đó không còn tồn tại trong mã nữa.

1. Truy cập giao diện AWS Secrets Manager service [console](https://console.aws.amazon.com/secretsmanager/home) 


2. Chọn **Store a new secret**.


3. Tại mục **Choose secret type page**, chọn **Credentials for RDS database**.
 - Nhập **User name** (``masteruser``)
 - Nhập **Password** mà bạn đã cung cấp khi tạo cụm DB trước đó.
 - Tiếp theo, trong phần **Select which RDS database this secret will access**, chọn DB instance của bạn (ví dụ: rdspg-fcj-labs). Nhấp vào **Next**.

4. Đặt tên cho secret `secretPostgresqlMasterUser` và nhập mô tả, sau đó click Next.

{{%notice note%}}
Hãy đảm bảo sử dụng tên chính xác (phân biệt chữ hoa chữ thường) của secretPostgresqlMasterUser để tránh phải chỉnh sửa một số câu lệnh trong bài lab sau này.
{{%/notice%}}

5. Cuối cùng, trong phần **Configure automatic rotation**, hãy chọn tùy chọn **Disable automatic rotation**. Trong môi trường production, bạn sẽ muốn sử dụng thông tin xác thực cơ sở dữ liệu tự động thay đổi để tăng cường bảo mật. Click **Next**.

6. Trong phần **Review** bạn có thể kiểm tra các thông số cấu hình trước khi nó được tạo. Nhấp vào **Store** ở cuối màn hình.

7. Sau khi tạo, hãy xác định **ARN** mới được tạo. Giá trị này sẽ cần thiết trong các phòng thí nghiệm tiếp theo. Trong list Secrets console, nhấp vào Secret name mới tạo.