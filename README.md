# ![aws](https://github.com/julien-muke/Search-Engine-Website-using-AWS/assets/110755734/01cd6124-8014-4baa-a5fe-bd227844d263)     AWS Control Tower and Landing Zone Hands-On


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



## ➡️ Set up a Landing Zone

1. Navigate to your console, search for "AWS Control Tower" then click on "Set up Landing Zone"


![Screenshot 2024-01-22 at 09 29 12](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/f6b77e55-ab27-4ac6-9d66-d539c1c494ae)



NOTE: when we create  our configuration in Control Tower, it's known as a landing zone, and that's the number  of accounts and configurations that are applied. Essentially, Control Tower is going to have the  ability to govern your resources across accounts and organizational units, but it's not going to  take control of everything by default. 


2. Review Pricing and Select Regoin

A. We need to define our "Home region". I'll leave mine on 'US East (North  Virginia)

B. The region deny setting can prohibit access to services based on your configuration.  So, if you enable that, then you can define which regions you want to actually control and the  preventive guardrails you want to use. I'm going to leave that one as not enabled. You can also  select additional regions now for governance. So, initially, it's just going to be 'US East  (North Virginia)'. Let's click on 'Next'


![Set-up-landing-zone-Control-Tower-us-east-1](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/ce5f0fd9-c26d-4b14-a0b9-3391d2200ab5)



3. Configure Organizational unit Structure

A. we can define the organizational unit structure.  The foundational OU, which is called 'Security' in this example, is where we're actually going  to have two shared accounts that will be the log archive account and the security audit account.  

B. Then, you can also create an additional OU if you wish to. This one's called 'Sandbox', and  you can create an account in there after setup, which you can then use for any kind of dev/test  workloads. Let's just leave the defaults, and I'm going to click on 'Next'


![Screenshot 2024-01-22 at 09 32 02](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/0c5147f8-36f3-4fd0-af3a-4cfef8974143)













