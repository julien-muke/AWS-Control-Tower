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



4. Configure the Shared Accounts and Encryption Settings

A. We can configure the shared accounts and Configure the Shared Accounts and Encryption Settings encryption settings. Now, we don't have anything  to change for the management account. That will be this account that I'm logged in with.

B. The log archive account is a repository for logs of api activities and resource configurations from all accounts in the landing zone.

C. The audit account is a restricted account that gives your security and compliance teams read and write access to all accounts in your landing zone

Let's provide email addresses for the log archive and audit accounts


![Set-up-landing-zone-Control-Tower-us-east-1 (1)](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/8abeea69-67bd-43e7-9800-3f0e7c33efb4)


D. Next, give aws control tower permissionto administer aws resources and enforce rules on your behalf and then finish setting up the landing zone.


![Screenshot 2024-01-22 at 09 46 12](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/86711942-9df9-4b5f-9c32-dc509d961209)


NOTE: Once your Control Tower configuration, your landing  zone, has been created, you'll see this message confirming what's happened, you can see the control tower dashboard:

* 2 organizational units have been created, 
* 3 shared accounts, a native cloud directory with pre-configured groups,  and single sign-on access
* 20 preventive guardrails to enforce policies and two detective  guardrails to detect configuration violations


![Dashboard-Control-Tower-us-east-1-2](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/7d6c6e4e-30fc-4ff2-ac29-5dbbf0646442)


👉 On the organizational units screen you can see the new OUs and your existing organizational units which remain unchanged from before control tower was set up because they are not managed by aws control tower


![Dashboard-Control-Tower-us-east-1-3](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/b4fb1f95-4f54-4b4d-81e3-d1593da20a7c)


👉 Let's look at the account factory:

The account factory enables you to create standardized baselines and network configurations for accounts in your organization let's see how you can use it to quickly enroll a new account in your organization.

A. To enroll a new account in your organization, choose "account factory" then click on "Create account"


![Screenshot 2024-01-22 at 10 51 20](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/cdc0fd38-c482-46de-a947-8b182181f6eb)


B. As a best practice for a well-architected multi-account environment aws control tower will set up accounts that offer isolated environments for specialized roles in your organization 

* Let's provide the basic information for the account including the account email address and display name 

* Next we'll designate the sso email and username next provide the first and last name intended for creating an aws sso user 

* Let's retain sandbox as the organizational unit and enroll the account you can monitor the creation of the account from aws service catalog 



![Create-account-Account-factory-Control-Tower-us-east-1-2](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/8f480f42-c522-4f7e-843b-35c716323234)



After a few minutes you can refresh the view to ensure the account is ready to use here you can see the newly enrolled account.


![Screenshot 2024-01-22 at 12 39 52](https://github.com/julien-muke/AWS-Control-Tower/assets/110755734/726dbdc7-0e6f-4404-80ac-eed8fb4733f5)



That's it for this tutorial. We've set up a landing  zone, and I've shown you around some of the basic configuration settings of your landing zone. And if you have set up in your account, then it's a good opportunity to play around a bit further and really understand how it all works.



## 💰 Cost

All services used are eligible for the AWS Free Tier. However, charges will incur at some point so it's recommended that you shut down resources after completing this tutorial.












