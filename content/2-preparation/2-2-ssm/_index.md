---
title : "AWS Secret Manager"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2.</b> "
---

#### Create an AWS Secrets Manager secret

**Secrets Manager** enables you to replace hardcoded credentials in your code, including passwords, with an API call to Secrets Manager to retrieve the secret programmatically. This helps ensure the secret can't be compromised by someone examining your code, because the secret no longer exists in the code.

1. Open the AWS Secrets Manager service [console](https://console.aws.amazon.com/secretsmanager/home) 


2. Choose **Store a new secret**.


3. On the **Choose secret type page**, choose **Credentials for RDS database**.
 - Input the **User name** (should be masteruser)
 - Input your **Password** that you provided when you created the DB cluster previously.
 - Next, in the **Select which RDS database this secret will access** section, choose the DB instance identifier you assigned to your instance (e.g. rdspg-fcj-labs). Click **Next**.

4. Name the secret `secretPostgresqlMasterUser` and provide a relevant description for the secret, then click Next.

{{%notice note%}}
Be sure to use the exact name (case-sensitive) of secretPostgresqlMasterUser to avoid having to edit some of the lab scripts later.
{{%/notice%}}

5. Finally, in the **Configure automatic rotation** section, leave the option of **Disable automatic rotation** selected. In a production environment you will want to use database credentials that rotate automatically for additional security. Click **Next**.

6. In the **Review** section you have the ability to check the configuration parameters for your secret, before it gets created. Additionally, you can retrieve sample code in popular programming languages, so you can easily retrieve secrets into your application. Click **Store** at the bottom of the screen.

7. Once created, identify the **ARN** of the newly created secret. This value will be needed in subsequent labs. In the list of Secrets in the console, click on the name of the newly created secret.