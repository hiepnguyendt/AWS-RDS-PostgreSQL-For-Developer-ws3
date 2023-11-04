---
title : "Code example for database connection"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

The labs in this section provide example implementations for programmatic access to RDS PostgreSQL instances. These can serve as a basic reference which can be used for actual implementations in applications.

1. [Simple database connection](3-1-sampledbconnect): In the first example, we create a database connection to the RDS PostgreSQL instance. The connection properties (DB endpoint, DB port, username and password) are fetched from environment variables.
2. [Auto-fetching instance credentials and connecting](3-2-autofetchingcredential): In the second example, we create a connection to the RDS PostgreSQL instance after fetching the connection properties by describing the RDS instance and fetching credentials from Secrets Manager using the AWS SDK. The AWS region is fetched from the AWS_REGION environment variable.
