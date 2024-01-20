# ![aws](https://github.com/julien-muke/Search-Engine-Website-using-AWS/assets/110755734/01cd6124-8014-4baa-a5fe-bd227844d263)     AWS Control Tower Overview and Landing Zone Hands-On


## 🤖 Introduction

In this AWS tutorial, you'll learn about AWS Control Tower and how you can use it to manage and govern many AWS accounts. You'll also have an opportunity to follow along as we show you how to create a Landing Zone using AWS Control Tower.

## 📝  AWS Control Tower Overview

👉  Control Tower creates a well-architected, multi-account baseline based on AWS best  practices

👉  And that's known as a landing zone 

👉 Guardrails are used for governance and compliance:

 * **Preventive guardrails**: Those are based on service control policies (SCPs), and they're  there to disallow API actions

* **Detective guardrails**: Those are implemented  using AWS Config rules and Lambda functions,  
and they're there to monitor and govern compliance  within the landing zone.

👉 The root user in the management  account can perform actions that guardrails  
would disallow.  This is the same concept as  with AWS Organizations, where the SCPs cannot  
affect the root user in the management account. 

In this tutorial, I'm going to show you the process Setting up a Landing Zone using AWS Control Tower for setting up a landing zone using AWS  Control Tower.



## 📐 Architecture Design


![Blank diagram-11](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/786ed493-5a4d-469d-ba5a-c0047744a0e6)




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