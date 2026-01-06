# Serverless-lead-capture-on-aws
A fully serverless lead capture & contact-us system built on AWS using S3, API Gateway, Lambda, DynamoDB, and SES.
This project demonstrates how to design, deploy, and operate a scalable, secure, and cost-effective serverless web application on AWS.


Architecture diagram/
└── serverless-lead-capture-architecture.png

📌 Project Overview

The solution follows a 3-phase architecture -
🔹 Phase 1: Static Website Hosting

Objective: Host a public website using Amazon S3.

Steps:

Created an S3 bucket

Enabled static website hosting

Configured bucket policy for public access

Uploaded website files using aws s3 sync

Added custom 404.html error page

✅ Website accessible via S3 website endpoint

🔹 Phase 2: Dynamic Contact Form (Serverless API)

Objective: Process contact form submissions.

Steps:

Created AWS Lambda function

Configured Amazon SES (email verification)

Created IAM role with:

CloudWatch Logs

SES SendEmail permissions

Created REST API in API Gateway

Enabled CORS

Integrated API Gateway with Lambda

Updated frontend JavaScript to POST data to API

✅ Form submissions trigger Lambda successfully

🔹 Phase 3: Data Management with DynamoDB

Objective: Persist contact messages.

Steps:

Created DynamoDB table ContactMessages

Partition key: id (String)

Updated Lambda role with dynamodb:PutItem

Enhanced Lambda function to:

Save form data to DynamoDB

Send email via SES

Verified records in DynamoDB

Verified logs in CloudWatch

✅ Leads are stored and emails are delivered


