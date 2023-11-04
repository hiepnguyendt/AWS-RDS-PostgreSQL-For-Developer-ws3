---
title : "Auto-fetching instance credentials and connecting"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---

#### Deploy the example code

1. To clone the repository from GitHub, you can use the following command:

```
git clone https://github.com/hiepnguyendt/Auto-fetching-instance-credentialsand-connecting.git
```

![autofetching](/images/2.2/1.png)

2. Eit file **.env** with your database credential

```
nano .env

```
![autofetching](/images/2.2/2.png)

- **AWS_REGION**: your region

![autofetching](/images/2.2/3.png)

3. Run the code:

```
npm start

```

![autofetching](/images/2.2/4.png)

Now, you are connecting to RDS PostgreSQL by Auto-fetching instance credentials from AWS Secret Manager.

{{%notice note%}}
If you got error when you run code. You should check AWS_regin in the AWS CLI  
{{%/notice%}}




