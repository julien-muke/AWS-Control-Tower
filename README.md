# ![aws](https://github.com/julien-muke/Search-Engine-Website-using-AWS/assets/110755734/01cd6124-8014-4baa-a5fe-bd227844d263)     AWS Control Tower Overview and Landing Zone Hands-On


## 🤖 Introduction

In this AWS tutorial, you'll learn how to build a simple event-driven and serverless application using Amazon SNS, Amazon SQS, and AWS Lambda. 


## 📐 Architecture Design


![Blank diagram-10](https://github.com/julien-muke/aws-serverless-app-with-sns-sqs/assets/110755734/a79f6fd4-7451-4ac6-bf7c-89d9c161f8c6)



## ⚙️ AWS Services Used

* Amazon Simple Notification Service (Amazon SNS)
* Amazon Simple Queue Service (Amazon SQS)
* AWS Lambda Function
* Amazon CloudWatch


## 🔋 Features



👉 The user is going to submit a notification to an SNS topic

👉 It's going to be integrated with a queue in other words the queue is subscribed to the topic and the message that we add to the topic ends up in the queue

👉 Then SQS is going to trigger a Lambda function

👉 The Lambda function is going to run and it's going to write some information to cloudwatch and whatever we put in the topic we're going to see that in Cloud watch logs