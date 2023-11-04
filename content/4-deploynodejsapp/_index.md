---
title : "Deploying AWS FCJ User Management System"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
#### AWS FCJ User Management System – Nodejs, Express, AWS RDS PostgreSQL, AWS Secret Manager & Handlebars, 

A user management system is a crucial component of many web applications. It allows admin manage their account information. In this tutorial, we will build a simple user management system using Node.js, Express, RDS PostgreSQL, and Handlebars.

- **Node.js** is a JavaScript runtime environment that allows us to build scalable and efficient server-side applications.
- **Express** is a lightweight web framework for Node.js that makes it easy to develop and maintain web applications. 
- **RDS PostgreSQL** is a managed database service from Amazon Web Services (AWS) that offers a reliable, scalable, and secure way to run PostgreSQL databases.
- **AWS Secrets Manager** is a service that helps you manage secrets, such as database passwords, API keys, and other sensitive information. This makes it easy to keep your secrets safe and secure.
- **Handlebars** is a templating engine that makes it easy to generate dynamic HTML pages.

![app](/images/3/0.jpg)

#### Deploy the application

1. To clone the repository from GitHub, you can use the following command:

```
git clone https://github.com/hiepnguyendt/fcj-management-user.git
```

![app](/images/3/1.png)

2. Eit file **.env** with your database credential

```
nano .env

```
![app](/images/3/2.png)

- **AWS_REGION**: your region

![autofetching](/images/2.2/3.png)

3. Run the code:

```
npm start

```

![app](/images/3/3.png)

***Now, you are connecting to RDS PostgreSQL by Auto-fetching instance credentials from AWS Secret Manager.***

{{%notice note%}}
If you got error when you run code. You should check AWS_regin in the AWS CLI  
{{%/notice%}}

4. Go to back **pgAdmin4** to query data
- Create table **`fcj_user`**

***You can using following SQL scripts below to create table ***
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

***You can using following SQL scripts below to insert data into table ***
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


5. Check **EC2 Instance status**: Make sure your EC2 Instance is running and functioning properly.

- Test the application in the browser: Open a web browser and enter the IP address or domain name of the EC2 Instance, followed by port 5000 (for example: http://<IP address or domain name> :5000). This will make a connection to your application running on port 5000.

- Test results: The browser will display your application if everything is configured correctly and the EC2 Instance is working. If not, you need to recheck the previous steps to identify the problem and fix it.

```
http://<IP address or domain name>:5000

```
![app](/images/3/6.png)


***Congratulation! You have built AWS FCJ User Management System on Amazon Web Services.***