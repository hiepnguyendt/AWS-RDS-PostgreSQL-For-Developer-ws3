---
title : "Set up enviroment"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1. </b> "
---

1. Using MobaXterm to SSH to EC2 instances
2. Install Node Version Manager (nvm)
    ```
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
    ```
![nodejs](/images/1/1.png/)

3. Active nvm and install Nodejs v16
    ```
    . ~/.nvm/nvm.sh
    nvm install 16
    ```
![nodejs](/images/1/2.png/)

4. Install Git
    ```
    sudo yum install git -y
    ```
![git](/images/1/3.png/)

5. Verify packages installation
    ```
    npm -v
    node -v
    git -v 
    ```
![verify](/images/1/7.png/)

6. Config your AWS CLI


![verify](/images/1/9.png/)

7. Install Nodemon
    ``` 
    npm install --save-dev nodemon
    ```

![verify](/images/1/8.png/)