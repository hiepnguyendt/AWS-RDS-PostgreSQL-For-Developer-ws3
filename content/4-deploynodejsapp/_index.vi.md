---
title : "Triển khai Hệ thống quản lý người dùng AWS FCJ"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
#### AWS FCJ User Management System – Nodejs, Express, AWS RDS PostgreSQL, AWS Secret Manager & Handlebars, 

Hệ thống quản lý người dùng là một thành phần quan trọng của nhiều ứng dụng web. Nó cho phép quản trị viên quản lý thông tin tài khoản của họ. Trong hướng dẫn này, chúng tôi sẽ xây dựng một hệ thống quản lý người dùng đơn giản bằng cách sử dụng Node.js, Express, RDS PostgreSQL và Handlebars.

- **Node.js** là một nền tảng phát triển ứng dụng được xây dựng trên JavaScript runtime của Chrome, cho phép bạn chạy mã JavaScript ở phía máy chủ. Nó cung cấp một môi trường thực thi đa luồng, không đồng bộ và có khả năng xử lý sự kiện, cho phép bạn xây dựng các ứng dụng mạng phía máy chủ hiệu quả.
- **Express** là một framework ứng dụng web phía máy chủ được xây dựng trên Node.js. Nó được thiết kế để đơn giản hóa việc xây dựng ứng dụng web và API bằng cách cung cấp các phương thức và công cụ giúp quản lý các yêu cầu (request) và phản hồi (response) trong ứng dụng web.
- **RDS PostgreSQL** là một dịch vụ cơ sở dữ liệu được quản lý từ Amazon Web Services (AWS) cung cấp một cách thức đáng tin cậy, có thể mở rộng và an toàn để chạy cơ sở dữ liệu PostgreSQL.
- **AWS Secrets Manager** là dịch vụ giúp bạn quản lý các bí mật, chẳng hạn như mật khẩu cơ sở dữ liệu, khóa API và các thông tin nhạy cảm khác. Điều này giúp bạn dễ dàng giữ bí mật của mình an toàn và bảo mật.
- **Handlebars** là một công cụ tạo khuôn mẫu giúp dễ dàng tạo các trang HTML động.

![app](/images/3/0.jpg)

#### Triển khai ứng dụng

1. Để clone code từ GitHub, bạn có thể sử dụng lệnh sau:
  ```
  git clone https://github.com/hiepnguyendt/fcj-management-user.git
  ```

![app](/images/3/1.png)

2. Chỉnh sửa file **.env** với thông tin xác thực cơ sở dữ liệu của bạn
  ```
  nano .env

  ```
![app](/images/3/2.png)

- **AWS_REGION**: your region

![autofetching](/images/2.2/3.png)

3. Chạy code:
  ```
  npm start

  ```

![app](/images/3/3.png)

***Bây giờ, bạn đang kết nối với RDS PostgreSQL bằng cách Tự động tìm nạp thông tin xác thực instance từ AWS Secret Manager.***

{{%notice note%}}
Nếu bạn gặp lỗi khi chạy mã. Bạn nên kiểm tra AWS_region trong AWS CLI
{{%/notice%}}

4.Trở lại giao diện **pgAdmin4** để truy vấn dữ liệu
- Create table **`fcj_user`**

***Bạn có thể sử dụng các tập lệnh SQL bên dưới để tạo bảng***
{{%expand "SQL Scripts" %}}

```
CREATE TABLE fcj_user
(
    id serial not null PRIMARY KEY, --create an auto-increment column id in a database table
    first_name VARCHAR(45) NOT NULL,
    last_name VARCHAR(45) NOT NULL,
    email VARCHAR(150) NOT NULL UNIQUE,
    phone VARCHAR(15) NOT NULL,
    courses VARCHAR(150) NOT NULL,
    status VARCHAR(10) NOT NULL DEFAULT 'active'
) 
```
![app](/images/3/4.png)

{{% /expand%}}



- Insert data into **fcj_user table**

***Bạn có thể sử dụng các tập lệnh SQL bên dưới để chèn dữ liệu vào bảng***
{{%expand "SQL Scripts" %}}

```
INSERT INTO fcj_user
(first_name, last_name, email, phone, courses, status)
VALUES
('Amanda', 'Nunes', 'anunes@ufc.com', '012345678910', 'AWS Certified Solutions Architect - Associate ', 'inactive'),
('Alexander', 'Volkanovski', 'avolkanovski@ufc.com', '012345678910', 'AWS Certified Developer - Associate', 'temp'),
('Khabib', 'Nurmagomedov', 'knurmagomedov@ufc.com', '012345678910', 'AWS Certified Advanced Networking - Specialty','active'),
('Kamaru', 'Usman', 'kusman@ufc.com', '012345678910', 'AWS Certified Data Analytics – Specialty','active'),
('Israel', 'Adesanya', 'iadesanya@ufc.com', '012345678910', 'AWS Certified Database – Specialty','active'),
('Henry', 'Cejudo', 'hcejudo@ufc.com', '012345678910', 'AWS Certified Solutions Architect - Associate','active'),
('Valentina', 'Shevchenko', 'vshevchenko@ufc.com', '012345678910', 'AWS Certified Advanced Networking - Specialty', 'inactive')

```
![app](/images/3/5.png)

{{% /expand%}}


5. Kiểm tra **EC2 Instance status**: Đảm bảo EC2 instance của bạn đang chạy và hoạt động bình thường.

- Kiểm tra ứng dụng trong trình duyệt: Mở trình duyệt web và nhập địa chỉ IP hoặc tên miền của EC2 instance, sau đó là port 5000 (ví dụ: http://<IP address or domain name> :5000). Điều này sẽ tạo kết nối tới ứng dụng của bạn chạy trên port 5000.

- Test results: Trình duyệt sẽ hiển thị ứng dụng của bạn nếu mọi thứ được cấu hình đúng và EC2 instance đang hoạt động. Nếu không, bạn cần kiểm tra lại các bước trước đó để xác định vấn đề và khắc phục.

```
http://<IP address or domain name>:5000

```
![app](/images/3/6.png)


***Chúc mừng! Bạn đã xây dựng Hệ thống quản lý người dùng AWS FCJ trên Amazon Web Services.***