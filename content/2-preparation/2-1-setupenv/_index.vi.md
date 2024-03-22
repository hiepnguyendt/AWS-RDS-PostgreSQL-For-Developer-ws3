---
title : "Thiết lập môi trường"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1. </b> "
---

1. Sử dụng MobaXterm để SSH tới các EC2 instance
2. Cài đặt Node Version Manager (nvm)
  ```
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
  ```

![nodejs](/images/1/1.png/)

3. Active nvm và cài đặt Nodejs v16
  ```
  . ~/.nvm/nvm.sh
  nvm install 16
  ```
![nodejs](/images/1/2.png/)

4. Cài đặt Git
  ```
  sudo yum install git -y
  ```
![git](/images/1/3.png/)

5. Xác minh cài đặt
  ```
  npm -v
  node -v
  git -v 
  ```
![verify](/images/1/7.png/)

6. Cấu hình AWS CLI của bạn


![verify](/images/1/9.png/)

7. Cài đặt Nodemon
  ``` 
  npm install --save-dev nodemon
  ```

![verify](/images/1/8.png/)