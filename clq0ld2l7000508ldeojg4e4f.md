---
title: "╚═★ 𝐷𝑎𝑦 03 𝐴𝑤𝑠 𝑍𝑒𝑟𝑜 𝑇𝑂 𝐻𝑒𝑟𝑜  ★═╝"
datePublished: Mon Dec 11 2023 07:27:48 GMT+0000 (Coordinated Universal Time)
cuid: clq0ld2l7000508ldeojg4e4f
slug: 03
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702279549953/d47860f3-b7a9-4bbe-b5ba-50ee5aa98b87.png
tags: aws, learning, cloud-computing, devops, learn-coding, learning-journey, trainwithshubham, aws-s3-for-beginners

---

🌐 Explore the Power of S3 Buckets in AWS! 🌐

What's an S3 Bucket? It's like your digital treasure chest 🎁, securely storing and retrieving any amount of data from anywhere on the web. 🌐 Imagine a limitless storage space where you can store, organize, and manage your files effortlessly! 💻

🔐 Security at its Best: S3 Buckets offer robust security features, ensuring your data is shielded with encryption, access controls, and logging. Rest easy knowing your information is in safe hands! 🛡️

⚙️ Scalability Unleashed: Whether you're a startup with big dreams or a global enterprise, S3 Buckets scale seamlessly to meet your evolving storage needs. From a few kilobytes to petabytes, AWS has got you covered! 📈

🌍 Global Accessibility: S3 Buckets provide low-latency access worldwide, making your data accessible to users and applications no matter where they are. Reach global heights with ease! 🌏

🔄 Versioning & Lifecycle Management: Keep track of changes with versioning, and optimize storage costs with lifecycle management. S3 Buckets empower you to manage your data lifecycle efficiently! 🔄

## What is IAM in AWS?

  
IAM, or Identity and Access Management, is a fundamental service provided by Amazon Web Services (AWS) that enables you to securely control access to your AWS resources. It's like the guardian of your AWS kingdom, allowing you to manage users, groups, and permissions with precision.

Here's a breakdown of key IAM features:

1. **User Management:**
    
    * IAM allows you to create and manage users within your AWS account.
        
    * Each user can be assigned unique security credentials (such as access keys, passwords) and specific permissions to control their access to AWS resources.
        
2. **Group Management:**
    
    * Users can be organized into groups, and permissions can be assigned to groups rather than individuals.
        
    * This streamlines the management of permissions, especially in large-scale environments.
        
3. **Role-Based Access Control (RBAC):**
    
    * IAM follows the RBAC model, where access permissions are assigned based on roles, allowing you to grant specific privileges to different roles within your organization.
        
4. **Fine-Grained Permissions:**
    
    * IAM provides fine-grained control over access to AWS resources. You can define precise permissions for users and groups, limiting their access to specific actions and resources.
        
5. **Multi-Factor Authentication (MFA):**
    
    * Enhance the security of your AWS accounts by enabling MFA for users. This adds an additional layer of protection, requiring users to present two or more pieces of evidence (factors) to gain access.
        
6. **Identity Federation:**
    
    * IAM supports identity federation, allowing users to access AWS resources using existing credentials from your corporate directory or other identity providers.
        
7. **Audit Trail:**
    
    * IAM provides detailed logging of API calls made on your account, offering an audit trail of who did what and when. This is crucial for security and compliance purposes.
        

## What is AWSCLI?

AWS Command Line Interface (AWS CLI) is a powerful and comprehensive tool provided by Amazon Web Services (AWS) to interact with AWS services directly from the command line. It's designed to make it easier to manage and automate various AWS resources and services, providing a command-line interface for AWS operations.

Key features of AWS CLI include:

1. **Cross-Platform Compatibility:**
    
    * AWS CLI is compatible with Windows, macOS, and Linux, making it accessible across a variety of operating systems.
        
2. **Wide Range of Services:**
    
    * It supports a broad spectrum of AWS services, allowing users to interact with services like EC2, S3, IAM, Lambda, and more, directly from the command line.
        
3. **Scripting and Automation:**
    
    * AWS CLI is scriptable, enabling users to create scripts and automate repetitive tasks. This is particularly useful for managing and deploying resources at scale.
        
4. **Flexible Output Formats:**
    
    * It provides options for controlling the output format, allowing users to receive data in JSON, text, or table formats, depending on their preference or automation needs.
        
5. **Profile Management:**
    
    * Users can configure and manage multiple profiles, allowing them to interact with different AWS accounts and regions seamlessly.
        
6. **Easy Installation and Updates:**
    
    * AWS CLI is easy to install and update, and AWS frequently releases updates to include support for new services and features.
        
7. **Integrated Help and Documentation:**
    
    * It includes a comprehensive help system that provides information on commands, options, and examples. Users can also access detailed documentation for each AWS service.
        

Here's a basic example of using AWS CLI to list the S3 buckets in your account:

[Home](https://k21academy.com/) / [Amazon Web Services](https://k21academy.com/category/amazon-web-services/) / How to Configure & Install AWS CLI?

# **How to Configure & Install AWS CLI?**

October 19, 2023 by [Hardik Tyagi](https://k21academy.com/author/hardikk21academy-com/) [Leave a Comment](https://k21academy.com/amazon-web-services/aws-cli/#respond)

*2961 views*

[**Why Command-line interface (CLI)**](https://k21academy.com/amazon-web-services/aws-cli/#2) **|** [**Benefits of CLI**](https://k21academy.com/amazon-web-services/aws-cli/#3) **|** [**Working of CLI**](https://k21academy.com/amazon-web-services/aws-cli/#4) **|** [**How to install and configure CLI**](https://k21academy.com/amazon-web-services/aws-cli/#5) **|** [**Case Study on AWS CLI**](https://k21academy.com/amazon-web-services/aws-cli/#6)

Cloud computing is getting popular among industries around the globe. Now, most enterprises are moving towards cloud computing and expanding their infrastructure footprints in the Cloud. [**Amazon Web Services (AWS**)](https://k21academy.com/amazon-web-services/overview-of-amazon-web-services-concepts/) is the market leader and top innovator in this field. One of the AWS tools is known as AWS CLI (Command-line interface)**.** It is used to manage AWS services through commands. This post will discuss what the AWS Command-line interface is and how to install & configure it.

**AWS supports two ways of infrastructure configurations for its Services.**

1.  Using AWS Web Console
    
2.  AWS Command-line interface (CLI)
    

## **What is AWS Command Line Interface**

**AWS CLI** is a unified configuration to administer AWS public cloud services. With only one tool, we can download, configure and monitor multiple AWS services using commands and automate them via scripts. Firstly we will set up CLI on any operating system like Windows, Linux, macOS, or Docker containers then it can access all the functionality provided on the AWS portal. Moreover, you can automate the managing and controlling process by writing the script in the programming language you are familiar with. That script allows deploying multiple resources without going through the entire configuration wizard each time. In simple, with the help of AWS CLI, you can manage and control all services from a terminal session in [**AWS Console**](https://k21academy.com/amazon-web-services/aws-management-console-walkthrough/)**.**

## **Why AWS Command Line interface?**

AWS Command line interface provides the best usability and control over AWS services. If there is another way available (AWS Web Console), why do we need a Command-line interface (CLI)?

![AWS Web console before AWS cli](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201151%20377'%3E%3C/svg%3E align="left")

Well, Infrastructure configuration through AWS Web console is quite a difficult and time-consuming process where AWS CLI comes into the picture and makes the configuration quick, easy, and efficient. It saves a lot of time and increases productivity among the working team.

![AWS Command-line interface after AWS cli](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201082%20357'%3E%3C/svg%3E align="left")

**Also Check:**  [**AWS Cloud Certification**](https://k21academy.com/aws-training-courses/).

## **Benefits of AWS Command Line Interface** 

One of the most obvious benefits of AWS CLI is the potential to save a significant amount of time. The savings come from easy installations, support of all services from one tool, going beyond GUIs, and using shell scripting to automate processes and commands. The major benefit of AWS CLI is mentioned below :

1. **Easy to Install:** Before CLI was introduced, we had something called the AWS EC2 Application programming tool kit, and installing this tool kit involves several difficult steps. The user has to set up multiple environment Variables which would be difficult to set up. Instead of this AWS, CLI is just a one-step process.
    
2. **Supports all AWS services:** AWS CLI is compatible with all the services like EC2, RDS, Beanstalk, SQS, SNS, etc.
    
3. **Time-Saving:** AWS command-line interfaces save a lot of time installing and managing AWS services. Because all the services are getting managed by commands and also we don’t have to follow traditional methods (through web console) to manage services.
    
4. **Scripting Automation:** It’s easy to automate the process of managing and controlling services by writing the script in any programming language.
    

**Read More:**  [**AWS MFA Service**](https://k21academy.com/amazon-web-services/aws-multi-factor-authentication-mfa/).

## **Working of AWS Command Line Interface** 

AWS CLI allows you to access files inside the portal through specific commands. It saves a lot of time and offers the ability to automate the entire process of controlling and managing AWS services through scripts. These scripts obtain a fully automated cloud infrastructure.

![AWS CLI Working](https://k21academy.com/wp-content/uploads/2021/04/AWS-CLI-Working-3.jpg align="left")

Using the terminal program, you can begin using all of the AWS Management Console features. It’s as follows:

**Linux shells:** Use a command shells program such as bash, ZHS, or THS to run commands. in operating systems like Linux, macOS, or Unix  
**Windows Command Line:** You can run commands in either the power shell or Windows command processor.  
**Remotely:** Remotely run commands on AWS EC2 instances through a remote terminal such as Putty, SSH, or AWS Systems Manager.

**Also Check:**  [**AWS Elastic Load Balancer**](https://k21academy.com/amazon-web-services/aws-elastic-load-balancing-overview-and-types/).

## **How to download and install AWS CLI For Windows:**

AWS Command Line Interface (AWS CLI) helps us interact with various AWS services in the cloud. These include your security credentials, default output format, and the default AWS Region.

**Prerequisites :** 

* Python 2 version 2.6.5+ or Python 3 version 3.3+
    
* Windows, Linux, macOS, or Unix Operating System
    

Now let’s install and configure AWS CLI  as shown in the following steps mentioned below:

**Step 1. Download and install AWS CLI:**  Before going to the AWS dashboard, firstly, we have to download the CLI installer on the local machine ( Windows, macOS, Linux ).

![Download AWS Installer form Official website](https://k21academy.com/wp-content/uploads/2021/04/Download-AWS-Installer-form-Offial-website.png align="left")

After that, RUN the downloaded MSI installer.

**Step 2. Confirm the installation**: To confirm the installation process, we must write the command `aws --version` prompt’s command. If the version is displayed, it indicates that CLI is installed, fortunately.

  
[Home](https://k21academy.com/) / [Amazon Web Services](https://k21academy.com/category/amazon-web-services/) / How to Configure & Install AWS CLI?

# **How to Configure & Install AWS CLI?**

October 19, 2023 by [Hardik Tyagi](https://k21academy.com/author/hardikk21academy-com/) [Leave a Comment](https://k21academy.com/amazon-web-services/aws-cli/#respond)

*2961 views*

[**Why Command-line interface (CLI)**](https://k21academy.com/amazon-web-services/aws-cli/#2) **|** [**Benefits of CLI**](https://k21academy.com/amazon-web-services/aws-cli/#3) **|** [**Working of CLI**](https://k21academy.com/amazon-web-services/aws-cli/#4) **|** [**How to install and configure CLI**](https://k21academy.com/amazon-web-services/aws-cli/#5) **|** [**Case Study on AWS CLI**](https://k21academy.com/amazon-web-services/aws-cli/#6)

Cloud computing is getting popular among industries around the globe. Now, most enterprises are moving towards cloud computing and expanding their infrastructure footprints in the Cloud. [**Amazon Web Services (AWS**)](https://k21academy.com/amazon-web-services/overview-of-amazon-web-services-concepts/) is the market leader and top innovator in this field. One of the AWS tools is known as AWS CLI (Command-line interface)**.** It is used to manage AWS services through commands. This post will discuss what the AWS Command-line interface is and how to install & configure it.

**AWS supports two ways of infrastructure configurations for its Services.**

1.  Using AWS Web Console
    
2.  AWS Command-line interface (CLI)
    

## **What is AWS Command Line Interface**

**AWS CLI** is a unified configuration to administer AWS public cloud services. With only one tool, we can download, configure and monitor multiple AWS services using commands and automate them via scripts. Firstly we will set up CLI on any operating system like Windows, Linux, macOS, or Docker containers then it can access all the functionality provided on the AWS portal. Moreover, you can automate the managing and controlling process by writing the script in the programming language you are familiar with. That script allows deploying multiple resources without going through the entire configuration wizard each time. In simple, with the help of AWS CLI, you can manage and control all services from a terminal session in [**AWS Console**](https://k21academy.com/amazon-web-services/aws-management-console-walkthrough/)**.**

## **Why AWS Command Line interface?**

AWS Command line interface provides the best usability and control over AWS services. If there is another way available (AWS Web Console), why do we need a Command-line interface (CLI)?

![AWS Web console before AWS cli](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201151%20377'%3E%3C/svg%3E align="left")

Well, Infrastructure configuration through AWS Web console is quite a difficult and time-consuming process where AWS CLI comes into the picture and makes the configuration quick, easy, and efficient. It saves a lot of time and increases productivity among the working team.

![AWS Command-line interface after AWS cli](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201082%20357'%3E%3C/svg%3E align="left")

**Also Check:**  [**AWS Cloud Certification**](https://k21academy.com/aws-training-courses/).

## **Benefits of AWS Command Line Interface** 

One of the most obvious benefits of AWS CLI is the potential to save a significant amount of time. The savings come from easy installations, support of all services from one tool, going beyond GUIs, and using shell scripting to automate processes and commands. The major benefit of AWS CLI is mentioned below :

1. **Easy to Install:** Before CLI was introduced, we had something called the AWS EC2 Application programming tool kit, and installing this tool kit involves several difficult steps. The user has to set up multiple environment Variables which would be difficult to set up. Instead of this AWS, CLI is just a one-step process.
    
2. **Supports all AWS services:** AWS CLI is compatible with all the services like EC2, RDS, Beanstalk, SQS, SNS, etc.
    
3. **Time-Saving:** AWS command-line interfaces save a lot of time installing and managing AWS services. Because all the services are getting managed by commands and also we don’t have to follow traditional methods (through web console) to manage services.
    
4. **Scripting Automation:** It’s easy to automate the process of managing and controlling services by writing the script in any programming language.
    

**Read More:**  [**AWS MFA Service**](https://k21academy.com/amazon-web-services/aws-multi-factor-authentication-mfa/).

## **Working of AWS Command Line Interface** 

AWS CLI allows you to access files inside the portal through specific commands. It saves a lot of time and offers the ability to automate the entire process of controlling and managing AWS services through scripts. These scripts obtain a fully automated cloud infrastructure.

![AWS CLI Working](https://k21academy.com/wp-content/uploads/2021/04/AWS-CLI-Working-3.jpg align="left")

Using the terminal program, you can begin using all of the AWS Management Console features. It’s as follows:

**Linux shells:** Use a command shells program such as bash, ZHS, or THS to run commands. in operating systems like Linux, macOS, or Unix  
**Windows Command Line:** You can run commands in either the power shell or Windows command processor.  
**Remotely:** Remotely run commands on AWS EC2 instances through a remote terminal such as Putty, SSH, or AWS Systems Manager.

**Also Check:**  [**AWS Elastic Load Balancer**](https://k21academy.com/amazon-web-services/aws-elastic-load-balancing-overview-and-types/).

## **How to download and install AWS CLI For Windows:**

AWS Command Line Interface (AWS CLI) helps us interact with various AWS services in the cloud. These include your security credentials, default output format, and the default AWS Region.

**Prerequisites :** 

* Python 2 version 2.6.5+ or Python 3 version 3.3+
    
* Windows, Linux, macOS, or Unix Operating System
    

Now let’s install and configure AWS CLI  as shown in the following steps mentioned below:

**Step 1. Download and install AWS CLI:**  Before going to the AWS dashboard, firstly, we have to download the CLI installer on the local machine ( Windows, macOS, Linux ).

![Download AWS Installer form Official website](https://k21academy.com/wp-content/uploads/2021/04/Download-AWS-Installer-form-Offial-website.png align="left")

After that, RUN the downloaded MSI installer.

**Step 2. Confirm the installation**: To confirm the installation process, we must write the command `aws --version` prompt’s command. If the version is displayed, it indicates that CLI is installed, fortunately.

![check if AWS cli is installed or not](https://k21academy.com/wp-content/uploads/2021/04/check-if-it-installed-or-not-1.png align="left")

**Check Out:** [**AWS VPC**](https://k21academy.com/amazon-web-services/aws-vpc-virtual-private-cloud/)

**Step 3. Configure AWS CLI:** After CLI installation, we have to download the AWS Console access key.

For that, go to **My Security Credentials**  ( Top right ) &gt; **choose Access keys** &gt; **Create New Access Key,** then download that key to the local machine.

![create new access key in AWS](https://k21academy.com/wp-content/uploads/2021/04/create-new-access-key.png align="left")

Now we can configure AWS CLI using the command: `aws configure` and fill in details like AWS keys, region, and output format.

1. AWS Access Key ID \[None\]: \*\*\*\*\*\*\*\*\*\*\*\*
    
2. AWS Secret access key \[None\]: \*\*\*\*\*\*\*\*\*\*\*\*
    
3. Default Region name \[None\]: us-east-2
    

(However, you can choose any region closest to your location)

1. Default output format \[None\]: JSON
    

(When we run the command, it’s going to split out some output, and there are several different options available, like how you want those outputs printed out. You can get it in JSON, YAML, or text format.)

```plaintext
aws s3 ls
```

Before using AWS CLI, you'll need to configure it with your AWS credentials and specify default settings like the region. Once configured, you can start using AWS CLI commands to manage your AWS resources efficiently.

## **1) Make a private S3 bucket in AWS and change the policy so you can access its stuff without making it public.**

Creating a Private S3 Bucket:

1. Access AWS Console: Log in to AWS and find the S3 service.
    
2. Bucket Creation: Click “Create Bucket” and follow the prompts, ensuring the bucket is private.
    
3. Policy Adjustment: Modify the bucket policy to allow your IAM user access while keeping it private.
    

Ensuring the security of your S3 bucket is crucial. Follow these simple steps to keep your data safe and accessible only to authorized users.

Creating a private S3 bucket in AWS and configuring the necessary policies to access its content without making it public involves a few steps. Below is a simplified guide using AWS CLI. Make sure you have the AWS CLI installed and configured with the necessary credentials.

### **Step 1: Create a Private S3 Bucket**

```plaintext
# Replace <your-unique-bucket-name> with a globally unique bucket name
aws s3 mb s3://<your-unique-bucket-name>
```

### **Step 2: Upload Objects to the Bucket**

```plaintext
# Upload a sample file to the bucket
echo "Hello, AWS S3!" > sample.txt
aws s3 cp sample.txt s3://<your-unique-bucket-name>/
```

### **Step 3: Configure Bucket Policy**

Create a file named `bucket-policy.json` with the following content. This policy grants read access to any authenticated AWS user, including yourself.

```plaintext
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<your-unique-bucket-name>/*"
    }
  ]
}
```

### **Step 4: Apply the Bucket Policy**

```plaintext
eaws s3api put-bucket-policy --bucket <your-unique-bucket-name> --policy file://bucket-policy.json
```

### **Step 5: Access the Objects**

You should now be able to access objects in your private bucket using AWS CLI.

```plaintext
aws s3 cp s3://<your-unique-bucket-name>/sample.txt .
cat sample.txt
```

Remember to replace `<your-unique-bucket-name>` with your actual bucket name.

This example policy is permissive. For a production scenario, consider limiting access to specific IAM users or roles and following the principle of least privilege. Ensure your bucket is appropriately secured based on your specific requirements and access control policies.

[Home](https://k21academy.com/) / [Amazon Web Services](https://k21academy.com/category/amazon-web-services/) / How to Configure & Install AWS CLI?

# **How to Configure & Install AWS CLI?**

October 19, 2023 by [Hardik Tyagi](https://k21academy.com/author/hardikk21academy-com/) [Leave a Comment](https://k21academy.com/amazon-web-services/aws-cli/#respond)

*2961 views*

[**Why Command-line interface (CLI)**](https://k21academy.com/amazon-web-services/aws-cli/#2) **|** [**Benefits of CLI**](https://k21academy.com/amazon-web-services/aws-cli/#3) **|** [**Working of CLI**](https://k21academy.com/amazon-web-services/aws-cli/#4) **|** [**How to install and configure CLI**](https://k21academy.com/amazon-web-services/aws-cli/#5) **|** [**Case Study on AWS CLI**](https://k21academy.com/amazon-web-services/aws-cli/#6)

Cloud computing is getting popular among industries around the globe. Now, most enterprises are moving towards cloud computing and expanding their infrastructure footprints in the Cloud. [**Amazon Web Services (AWS**)](https://k21academy.com/amazon-web-services/overview-of-amazon-web-services-concepts/) is the market leader and top innovator in this field. One of the AWS tools is known as AWS CLI (Command-line interface)**.** It is used to manage AWS services through commands. This post will discuss what the AWS Command-line interface is and how to install & configure it.

**AWS supports two ways of infrastructure configurations for its Services.**

1.  Using AWS Web Console
    
2.  AWS Command-line interface (CLI)
    

## **What is AWS Command Line Interface**

**AWS CLI** is a unified configuration to administer AWS public cloud services. With only one tool, we can download, configure and monitor multiple AWS services using commands and automate them via scripts. Firstly we will set up CLI on any operating system like Windows, Linux, macOS, or Docker containers then it can access all the functionality provided on the AWS portal. Moreover, you can automate the managing and controlling process by writing the script in the programming language you are familiar with. That script allows deploying multiple resources without going through the entire configuration wizard each time. In simple, with the help of AWS CLI, you can manage and control all services from a terminal session in [**AWS Console**](https://k21academy.com/amazon-web-services/aws-management-console-walkthrough/)**.**

## **Why AWS Command Line interface?**

AWS Command line interface provides the best usability and control over AWS services. If there is another way available (AWS Web Console), why do we need a Command-line interface (CLI)?

![AWS Web console before AWS cli](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201151%20377'%3E%3C/svg%3E align="left")

Well, Infrastructure configuration through AWS Web console is quite a difficult and time-consuming process where AWS CLI comes into the picture and makes the configuration quick, easy, and efficient. It saves a lot of time and increases productivity among the working team.

![AWS Command-line interface after AWS cli](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201082%20357'%3E%3C/svg%3E align="left")

**Also Check:**  [**AWS Cloud Certification**](https://k21academy.com/aws-training-courses/).

## **Benefits of AWS Command Line Interface** 

One of the most obvious benefits of AWS CLI is the potential to save a significant amount of time. The savings come from easy installations, support of all services from one tool, going beyond GUIs, and using shell scripting to automate processes and commands. The major benefit of AWS CLI is mentioned below :

1. **Easy to Install:** Before CLI was introduced, we had something called the AWS EC2 Application programming tool kit, and installing this tool kit involves several difficult steps. The user has to set up multiple environment Variables which would be difficult to set up. Instead of this AWS, CLI is just a one-step process.
    
2. **Supports all AWS services:** AWS CLI is compatible with all the services like EC2, RDS, Beanstalk, SQS, SNS, etc.
    
3. **Time-Saving:** AWS command-line interfaces save a lot of time installing and managing AWS services. Because all the services are getting managed by commands and also we don’t have to follow traditional methods (through web console) to manage services.
    
4. **Scripting Automation:** It’s easy to automate the process of managing and controlling services by writing the script in any programming language.
    

**Read More:**  [**AWS MFA Service**](https://k21academy.com/amazon-web-services/aws-multi-factor-authentication-mfa/).

## **Working of AWS Command Line Interface** 

AWS CLI allows you to access files inside the portal through specific commands. It saves a lot of time and offers the ability to automate the entire process of controlling and managing AWS services through scripts. These scripts obtain a fully automated cloud infrastructure.

![AWS CLI Working](https://k21academy.com/wp-content/uploads/2021/04/AWS-CLI-Working-3.jpg align="left")

Using the terminal program, you can begin using all of the AWS Management Console features. It’s as follows:

**Linux shells:** Use a command shells program such as bash, ZHS, or THS to run commands. in operating systems like Linux, macOS, or Unix  
**Windows Command Line:** You can run commands in either the power shell or Windows command processor.  
**Remotely:** Remotely run commands on AWS EC2 instances through a remote terminal such as Putty, SSH, or AWS Systems Manager.

**Also Check:**  [**AWS Elastic Load Balancer**](https://k21academy.com/amazon-web-services/aws-elastic-load-balancing-overview-and-types/).

## **How to download and install AWS CLI For Windows:**

AWS Command Line Interface (AWS CLI) helps us interact with various AWS services in the cloud. These include your security credentials, default output format, and the default AWS Region.

**Prerequisites :** 

* Python 2 version 2.6.5+ or Python 3 version 3.3+
    
* Windows, Linux, macOS, or Unix Operating System
    

Now let’s install and configure AWS CLI  as shown in the following steps mentioned below:

**Step 1. Download and install AWS CLI:**  Before going to the AWS dashboard, firstly, we have to download the CLI installer on the local machine ( Windows, macOS, Linux ).

![Download AWS Installer form Official website](https://k21academy.com/wp-content/uploads/2021/04/Download-AWS-Installer-form-Offial-website.png align="left")

After that, RUN the downloaded MSI installer.

**Step 2. Confirm the installation**: To confirm the installation process, we must write the command `aws --version` prompt’s command. If the version is displayed, it indicates that CLI is installed, fortunately.

![check if AWS cli is installed or not](https://k21academy.com/wp-content/uploads/2021/04/check-if-it-installed-or-not-1.png align="left")

**Check Out:** [**AWS VPC**](https://k21academy.com/amazon-web-services/aws-vpc-virtual-private-cloud/)

**Step 3. Configure AWS CLI:** After CLI installation, we have to download the AWS Console access key.

For that, go to **My Security Credentials**  ( Top right ) &gt; **choose Access keys** &gt; **Create New Access Key,** then download that key to the local machine.

![create new access key in AWS](https://k21academy.com/wp-content/uploads/2021/04/create-new-access-key.png align="left")

Now we can configure AWS CLI using the command: `aws configure` and fill in details like AWS keys, region, and output format.

1. AWS Access Key ID \[None\]: \*\*\*\*\*\*\*\*\*\*\*\*
    
2. AWS Secret access key \[None\]: \*\*\*\*\*\*\*\*\*\*\*\*
    
3. Default Region name \[None\]: us-east-2
    

(However, you can choose any region closest to your location)

1. Default output format \[None\]: JSON
    

(When we run the command, it’s going to split out some output, and there are several different options available, like how you want those outputs printed out. You can get it in JSON, YAML, or text format.)

![CLI configuration ](https://k21academy.com/wp-content/uploads/2021/04/configration-done.png align="left")

**Step 4. Create Key Pair through CLI:** Now, let’s create a key pair with the help of the command :`aws ec2 create-key-pair --key-name mycloudkey --query 'KeyMaterial' --output text > malik.pem`

  
If you want to delete the key pair at some instance, you can use the command: `aws ec2 delete-key-pair --key-name malik.pem (key pair name )`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702278834506/43452aa4-b9c2-4950-a920-93baba83d24a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702278843630/0a608e16-b73a-401f-8956-24ea59e313a5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702278847070/1af8f409-93d0-427e-92d5-7fa24d4bedb0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702278850320/3d1e3571-cd00-44b7-8db7-3608c092a34c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702278853324/69dd6c6d-f1e3-4b8d-9209-fc6a9af4b4ef.png align="center")