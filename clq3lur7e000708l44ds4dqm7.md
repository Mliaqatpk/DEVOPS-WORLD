---
title: "dₐy ₀₄ ₐws zₑᵣₒ tₒ ₕₑᵣₒ"
datePublished: Wed Dec 13 2023 10:04:52 GMT+0000 (Coordinated Universal Time)
cuid: clq3lur7e000708l44ds4dqm7
slug: dy-ws-z-t
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702462161500/d99eb618-3d42-4cff-adbf-585ba4982e8f.png
tags: cloud, aws, cloud-computing, aws-lambda, shubhamlondhe, trainwithshubham, aws-zero-to-hero

---

# AWS RDS, DynamoDB and AWS lambda

![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--Lr6Hf676--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/iimpyc8ndm7vnn6arhp3.gif align="left")

![](https://miro.medium.com/v2/resize:fit:850/1*kulXFyTaywex_aU6eUyPRA.png align="left")

Amazon Web Services (AWS) provides a suite of cloud computing services that cater to various business needs. Among these services, Amazon RDS (Relational Database Service), Amazon DynamoDB, and AWS Lambda are key components that play crucial roles in building scalable, flexible, and efficient cloud-based applications.

### **Amazon RDS (Relational Database Service):**

**Overview:** Amazon RDS is a managed relational database service that makes it easier to set up, operate, and scale a relational database in the cloud. It supports several database engines, including MySQL, PostgreSQL, Oracle, Microsoft SQL Server, and Amazon Aurora.

**Key Features:**

1. **Managed Service:** AWS RDS takes care of routine database tasks such as backups, patch management, and scaling, allowing developers to focus more on application development.
    
2. **Multi-AZ Deployments:** RDS supports Multi-AZ (Availability Zone) deployments for high availability and automatic failover. This ensures that if one AZ becomes unavailable, the system automatically redirects to another AZ.
    
3. **Security:** RDS provides features such as encryption at rest and in transit, network isolation using Amazon VPC, and IAM integration for fine-grained access control.
    
4. **Scalability:** With features like Read Replicas and Aurora Auto-Scaling, RDS enables users to scale their database horizontally and vertically based on the application's needs.
    

### **Amazon DynamoDB:**

**Overview:** DynamoDB is a fully managed NoSQL database service provided by AWS. It is designed to provide low-latency and seamless scalability for applications with variable and unpredictable workloads.

**Key Features:**

1. **Managed NoSQL:** DynamoDB is a fully managed NoSQL database that eliminates the administrative overhead of operating and scaling a distributed database.
    
2. **Scalability:** It can scale both read and write capacity independently, allowing applications to handle varying workloads with ease.
    
3. **Performance:** DynamoDB provides single-digit millisecond latency for read and write operations, making it suitable for applications that require low-latency access to data.
    
4. **Serverless Integration:** DynamoDB integrates seamlessly with AWS Lambda, allowing developers to build serverless applications with a fully managed backend.
    

### **AWS Lambda:**

**Overview:** AWS Lambda is a serverless computing service that enables developers to run code without provisioning or managing servers. It automatically scales and manages the infrastructure needed to run applications, allowing developers to focus on writing code.

**Key Features:**

1. **Event-Driven Programming:** Lambda functions are triggered by events such as changes to data in an Amazon S3 bucket, updates to an Amazon DynamoDB table, or an HTTP request through Amazon API Gateway.
    
2. **Pay-Per-Use Pricing:** With Lambda, you pay only for the compute time that you consume. There are no upfront costs, and you don't have to pay for idle compute capacity.
    
3. **Integration with AWS Services:** Lambda seamlessly integrates with various AWS services, including RDS and DynamoDB. This integration enables developers to build powerful and scalable applications by combining the strengths of different AWS services.
    
4. **Multi-Language Support:** Lambda supports multiple programming languages, allowing developers to use their preferred language to write functions.
    

### **Integration of RDS, DynamoDB, and Lambda:**

Developers often use a combination of RDS, DynamoDB, and Lambda to build scalable and cost-effective applications. For example, Lambda functions can be triggered by events from DynamoDB tables or can interact with RDS databases to perform specific tasks. This serverless architecture enables developers to build applications that automatically scale based on demand, without the need to manage the underlying infrastructure.

## Tasks:

#### 1) Read about AWS RDS, DynamoDB and AWS lambda and write a post on linkedIn with example in your own words.

> `Note:` I have added documentation for reference below

#### 2) You are part of a team responsible for migrating the database of an existing e-commerce platform to Amazon RDS. The goal is to improve scalability, performance, and manageability. The current setup uses a self-managed MySQL database on an on-premises server. 👇

#### What needs to be done:

* Set up and configure a MySQL database on AWS RDS, ensuring optimal performance.
    
* Establish a connection between the RDS instance and your EC2 environment
    

#### 3) Deploy a scalable web application. The application consists of a MySQL database managed by Amazon RDS and a flask based web application that automatically scale based on demand using an Auto Scaling group and an Elastic Load Balancer.

* Deploy this: [Two-tier application](https://github.com/LondheShubham153/two-tier-flask-app)
    

#### 4) Scenario:

You're an AWS expert managing a budget-friendly project with EC2 instances. To save money, you're using AWS Lambda to automatically start and stop instances when they're not needed during non-business hours. 👇

#### What needs to be done:

* Create an AWS Lambda function that will start/stop instances based on their instance tag.
    

## **TASK 2 :**

1)Set up and configure a MySQL database on AWS RDS, ensuring optimal performance.

2)Establish a connection between the RDS instance and your EC2 environment.

### **MySQL on Amazon RDS**

**Configuring Amazon RDS:**

1. **Database Instance Creation:** Navigate to the AWS Management Console, select Amazon RDS, and create a new database instance. Choose MySQL as the engine.
    
2. **Instance Settings:** Define your instance details, including DB credentials, storage, and network configurations.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702279468236/fb7689d7-4bda-4d42-b4f5-2ef7f4c5a1b8.png?auto=compress,format&format=webp align="left")

**Connecting EC2 to RDS:**

Go to your RDS database. Scroll to the "**Connected compute resources**" section --&gt; click on 'Actions' --&gt;'Set up EC2connection' and add your ec2 instance( ex: webserver1-ec2).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702279709480/bebfb1ae-b486-490e-aa47-bba8fcbec006.png?auto=compress,format&format=webp align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702279821577/19a26cb1-2bec-46d0-a9a1-abdc1923a130.png?auto=compress,format&format=webp align="left")

## **TASK 3 :**

### **Deploy a scalable web application.**

### **The application consists of a MySQL database managed by Amazon RDS and a flask based web application that automatically scale based on demand using an Auto Scaling group and an Elastic Load Balancer.**

**Step 1: Creation of a webserver**

1)Created launch template.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702280230797/e96e4891-3a36-432e-8375-4b8adb390f3a.png?auto=compress,format&format=webp align="left")

2)Created Auto sacling group with desired capacity -1,min capacity-1,max.capacity-2.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702280532927/19510416-3178-4c86-9200-7da696b4fee2.png?auto=compress,format&format=webp align="left")

3)created an Application loadbalancer with a target group(webserver-targetgp)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702280846324/80cfa06f-e4d8-4666-9284-5c9b835ecf40.png?auto=compress,format&format=webp align="left")

Now, an instance for our flask app is created with high availabilty and scalability.

**Step 2:Dockerization of Web Application**

1. **Cloning the Repository:** Clone [**this repository**](https://github.com/LondheShubham153/two-tier-flask-app/tree/master) which contains the Dockerfile.
    
2. **Image Creation:** Execute `docker build` to create an image from your Dockerfile. This encapsulates your app and its dependencies.
    

**Step 3:**

* In your instance terminal, run the following commands.navigate to the RDS homepage, select the database you have already created (named "**database-1**"), copy the **endpoint**, and paste it here.
    

```plaintext
     # Install mysql client
   sudo apt update
   sudo apt install mysql-client

   # Connecting your ec2 instance to the rds database.
   mysql -u admin -h <endpoint> -P 3306 -p
```

* Then,enter the [password.Now](https://anjumohan.hashnode.dev/aws-zero-to-hero-day04#heading-mysql-on-amazon-rds) we can see the mysql monitor and run the following commands for creating a new database.
    

```plaintext
create database db1;
#select db1
use db1;


#create the table
   CREATE TABLE messages (
       id INT AUTO_INCREMENT PRIMARY KEY,
       message TEXT
   );
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702282089563/11eb88d8-8502-4e73-b2e4-622ed4b79c1b.png?auto=compress,format&format=webp align="left")

**Step4:Deployment**

1. **Running the docker container:** Run the docker container using the following command.
    

```plaintext
   sudo docker run -d -p 5000:5000 -e MYSQL_HOST=<endpoint> -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin123 -e MYSQL_DB=db1 two-tier
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702282447113/90ff8c8c-90cb-4bb4-89f4-1ddb433934b7.png?auto=compress,format&format=webp align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702461756125/e3642fbb-9487-4962-88ae-b031fbc651ec.png align="center")

**Step 5:Check the result**

Check the url on your browser `http://<ec2-public-ip>:5000`.

Now,you can see that our **Two-tier flsakapp** is unning successfully.

### TASK 4 - Scenario:

You're an AWS expert managing a budget-friendly project with EC2 instances. To save money, you're using AWS Lambda to automatically start and stop instances when they're not needed during non-business hours.

#### What needs to be done:

Create an AWS Lambda function that will start/stop instances based on their instance tag.

**Solution:**

For this task, I am demonstrating how to stop an instance using AWS Lambda. For reference, please watch this [document.**AWS**](https://anjumohan.hashnode.dev/aws-zero-to-hero-day04#heading-mysql-on-amazon-rds) [**LAMBDA**](https://repost.aws/knowledge-center/start-stop-lambda-eventbridge)

**Step1**: **Create an ec2 instance.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702312248713/18513f88-835d-4e74-8fac-a658b34aaf1f.png?auto=compress,format&format=webp align="left")

**Step2: create IAM policy**

Use the JSON policy editor to create an IAM policy. Paste the following JSON policy document into the policy editor.(refer the above doc)

**Step3: Create IAM role for Lambda**

**Important:** When you attach a permissions policy to Lambda, make sure that you choose the IAM policy.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702312620010/2e6c21b9-1e9a-4a6e-b713-9ddb78dd9604.png?auto=compress,format&format=webp align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702312725936/6c91ef7a-5e1c-4004-b1c3-58e9076750f6.png?auto=compress,format&format=webp align="left")

**Step 4: Create Lambda function**

1. Open the [**Lambda console**](https://console.aws.amazon.com/lambda/), and then choose **Create function**.
    
2. On the **Code** tab, under **Code source**, paste the following code for stopping instances (refer [**AWS LAMBDA**](https://repost.aws/knowledge-center/start-stop-lambda-eventbridge)).
    
3. Replace **us-west-1** with the AWS Region that your instances are in. Replace **InstanceIds** with the IDs of the instances that you want to stop and start.
    

**Step 5:Test your Lambda functions**

In the **Code source** section, choose **Test.**Enter an **Event name.** Then, choose **Create**.  
Choose **Test** to run the function.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702313451671/fef1a1b0-49d2-4672-a643-8055b567d005.png?auto=compress,format&format=webp align="left")

Now, go back to your instances page and check the status of the mentioned instance; yes, **it's stopped**. You can also start/stop instances automatically by using a Lambda function with EventBridge rules.