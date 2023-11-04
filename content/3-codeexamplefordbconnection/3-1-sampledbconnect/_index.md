---
title : "Simple database connection"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

#### Deploy simple code

1. To clone the repository from GitHub, you can use the following command:

```
git clone https://github.com/hiepnguyendt/sample-database-connection.git
```

![simplecode](/images/2.1/1.png)

2. Eit file **.env** with your database credential

```
nano .env

```
![simplecode](/images/2.2/4.png)

- **DB_USER**: 'your username'  
- **DB_PASS**: 'your password'
- **DB_HOST**: 'endpoint your RDS PostgreSQL'
- **DB_PORT**: '5432'

![simplecode](/images/2.1/3.png)

3. Run the code:

```
npm start
```

![simplecode](/images/2.1/2.png)

Now, you are connecting to RDS PostgreSQL with:
- **User**: masteruser
- **Database**: pglab
- **Port**: 5432