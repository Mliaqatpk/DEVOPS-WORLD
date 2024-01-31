---
title: "Day 41 Setting up an Application Load Balancer with AWS EC2 🚀 ☁"
datePublished: Wed Jan 31 2024 09:40:28 GMT+0000 (Coordinated Universal Time)
cuid: cls1lk4ur000a09jp4ynt2k88
slug: day-41-setting-up-an-application-load-balancer-with-aws-ec2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706693928221/0d4ffebf-4985-4f5b-92bf-dee8178c0cf7.png
tags: cloud, authentication, aws, cloud-computing, automation, devops, devops-articles, 90daysofdevops, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, batch-5

---

Hey Techies! Welcome to this blog

In this blog, we are going to start with Setting up an Application Load Balancer with AWS EC2 🚀 ☁

*What is an AWS Application Load Balancer?*

*✅ It’s a layer seven load balancer platform  
✅ Supports path and host-based routing to allow the request to be routed to different application  
✅ Supports HTTP/2 and WebSockets*

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704111507858/c6156d49-5971-4a77-aeb2-70be1220e2eb.webp?auto=compress,format&format=webp align="left")

### **Elastic Load Balancing:**

**Elastic Load Balancing (ELB)** is a service provided by Amazon Web Services (AWS) that automatically distributes incoming traffic across multiple EC2 instances. ELB provides three types of load balancers:

1. **Application Load Balancer (ALB)** - *operates at layer 7 of the OSI model and is ideal for applications that require advanced routing and microservices.*
    
2. **Network Load Balancer (NLB)** - *operates at layer 4 of the OSI model and is ideal for applications that require high throughput and low latency.*
    
3. **Classic Load Balancer (CLB)** - *operates at layer 4 of the OSI model and is ideal for applications that require basic load balancing features.*
    

### **What is Load Balancing..??**

Load balancing is the process of distributing network traffic across multiple servers to ensure that no single server is overwhelmed with requests. The main purpose of load balancing is to improve the reliability, scalability, and performance of web applications by distributing traffic across multiple servers.

### **What is Elastic Load Balancing..?**

Elastic Load Balancing (ELB) is a service provided by Amazon Web Services (AWS) that automatically distributes incoming traffic across multiple EC2 instances. ELB provides three types of load balancers: Application Load Balancer (ALB), Network Load Balancer (NLB), and Classic Load Balancer (CLB).

By distributing traffic across multiple instances, ELB helps improve the reliability and availability of your applications, as well as their performance and scalability.

### **Elastic Load Balancing**

AWS Load Balancers are virtual devices or services that distribute incoming network traffic across multiple targets, such as Amazon EC2 instances, containers, or IP addresses, to ensure your applications are highly available, fault-tolerant, and performant.

### **How Elastic Load Balancing Works**

![AWS ELB - Elastic Load Balancer | Why and What is ELB? | What are listeners  and target groups? - YouTube](https://i.ytimg.com/vi/fMgA3rE0aPY/maxresdefault.jpg align="left")

A load balancer accepts incoming traffic from clients and routes requests to its registered targets (such as EC2 instances) in one or more Availability Zones.

The load balancer also monitors the health of its registered targets and ensures that it routes traffic only to healthy targets. When the load balancer detects an unhealthy target, it stops routing traffic to that target. It then resumes routing traffic to that target when it detects that the target is healthy again.

### **Key Features & Benefits of Elastic Load Balancing**

* **High Availability**: Load balancers distribute traffic across multiple instances, reducing the risk of a single point of failure and ensuring high availability.
    
* **Auto Scaling**: Load balancers can work with auto-scaling groups to automatically adjust the number of instances based on traffic load.
    
* **Security**: Load balancers can act as a shield against distributed denial-of-service (DDoS) attacks by providing protection and mitigation services.
    
* **SSL/TLS Termination**: They can offload SSL/TLS encryption and decryption, reducing the processing burden on your backend instances.
    
* **Session Management**: Some load balancers support session affinity, which ensures that a user's requests are consistently sent to the same backend instance.
    

### **AWS Load Balancer Types**

There are four AWS load balancer types supported

![LoadBalancers_Diagram](https://k21academy.com/wp-content/uploads/2020/09/LoadBalancers_Diagram.png align="left")

### **Classic Load Balancer**

* **Classic Load Balancer (CLB)** is a legacy load balancer that is no longer recommended for new applications. It is a Layer 4 load balancer
    
* Supports HTTP, HTTPS, TCP, and SSL listeners and supports sticky sessions using application-generated cookies.
    
* **AWS has announced that CLB will be deprecated on December 31, 2022**.
    

### **Application Load Balancer**

* AWS Elastic Load Balancing automatically distributes incoming traffic across `multiple targets, such as EC2 instances, containers, and IP addresses`, in one or more Availability Zones.
    
* The Load Balancer distributes the traffic to the appropriate `Target Groups`.
    
* New feature-rich, `layer 7` load-balancing platform.
    
* Supports `web sockets, HTTP, HTTPS, microservices, and container-based applications`, including deep integration with EC2 container service.
    
* Support for `path-based and host-based routing`. Also, provide routing requests to multiple applications on a single EC2 instance.
    
* `Cross-zone load balancing` is always enabled and you can also specify Lambda functions are targeted to serve HTTP(S) requests.
    
* Supports load balancer-generated cookies only for sticky sessions.
    
* **Key Components of an Application Load Balancer:**
    
    1. **Listeners:** ALB uses listeners to check for connection requests from clients. These listeners are configured with specific protocols and ports and are at the forefront of routing decisions.
        
    2. **Rules:** Listener rules define how the load balancer routes requests to its registered targets. Each rule consists of a priority, one or more actions, and conditions. Rules allow for sophisticated traffic management based on various factors.
        
    3. **Target Groups:** These groups route requests to registered targets, such as EC2 instances, using specified protocols and port numbers. A target can be registered with multiple target groups, and health checks can be configured per target group
        

![Application load balancer](https://k21academy.com/wp-content/uploads/2020/08/illustration-2.png align="left")

### **Network Load balancer**

* **Network Load Balancer (NLB)** shines as a high-performance solution designed to operate at the `transport layer (Layer 4)` of the Open Systems Interconnection (OSI) model.
    
* Connection baseload Balancing and it supports `TCP protocol`.
    
* Support for static IP addresses for the load balancer. or assign one Elastic IP address per subnet enabled for the load balancer.
    
* Cross-zone load balancing is disabled by default.
    
* **Key Components of a Network Load Balancer:**
    
    1. **Listeners**: NLB uses listeners to check for incoming connection requests from clients. Listeners are configured with specific protocols and ports, serving as the entry point for traffic.
        
    2. **Target Groups**: These groups route incoming requests to registered targets, which can be EC2 instances or IP addresses. You can also configure target groups to support various protocols like TCP, UDP, TCP\_UDP, and TLS, providing flexibility.
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697868300430/9ff452d6-85d1-402f-88aa-54adae57f261.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

### **Gateway Load Balancer**

* Gateway Load Balancer (GWLB) stands out as a specialized solution tailored for deploying and managing virtual appliances.
    
* It makes it simple to scale, install, and manage your third-party virtual appliances.
    
* Provide you with one gateway for distributing traffic across multiple virtual appliances, while scaling them up, or down, based on demand.
    
* **Gateway Load Balancer Endpoints:**
    
    * GWLB uses Gateway Load Balancer endpoints to securely exchange traffic across Virtual Private Cloud (VPC) boundaries
        

![AWS Gateway Load Balancer 1O1. Digital equipment such as firewalls… | by  Piyush Jalan | Medium](https://miro.medium.com/v2/resize:fit:1121/1*qNMaVza5BzgrimG2fz0gNg.png align="left")

### Task 1:

* launch 2 EC2 instances with an Ubuntu AMI and use User Data to install the Apache Web Server.
    
* Modify the index.html file to include your name so that when your Apache server is hosted, it will display your name also do it for 2nd instance which include " TrainWithShubham Community is Super Aweasome :) ".
    
* Copy the public IP address of your EC2 instances.
    
* Open a web browser and paste the public IP address into the address bar.
    
* You should see a webpage displaying information about your PHP installation.
    

**Launch EC2 Instances:**

* Open the AWS Management Console.
    
* Navigate to the EC2 Dashboard.
    
* Click on "Launch Instance."
    
* Choose an Ubuntu AMI.
    
* In the "Configure Instance Details" section, add the following script in the "User Data" field:
    
    ```plaintext
        bash
    ```
    
    ```plaintext
         #!/bin/bash
         apt-get update
         apt-get install -y apache2
         echo "<html><body><h1>Your Name</h1></body></html>" > /var/www/html/index.html
    ```
    
    * Complete the instance creation wizard, and launch two instances.
        

1. **Modify Index.html:**
    
    * SSH into each instance using the public IP addresses.
        
    * Edit the `/var/www/html/index.html` file on each instance.
        
        * Instance 1: Add your name.
            
        * Instance 2: Add "My Website".
            
2. **Copy Public IP Addresses:**
    
    * In the EC2 Dashboard, copy the public IP addresses of both instances.
        
3. **Test Apache Web Server:**
    
    * Open a web browser and paste the public IP addresses into the address bar.
        

### Task 2:

* Create an Application Load Balancer (ALB) in EC2 using the AWS Management Console.
    
* Add EC2 instances which you launch in task-1 to the ALB as target groups.
    
* Verify that the ALB is working properly by checking the health status of the target instances and testing the load balancing capabilities.
    

[![LoadBalancer](https://user-images.githubusercontent.com/115981550/218143557-26ec33ce-99a7-4db6-a46f-1cf48ed77ae0.png align="left")](https://user-images.githubusercontent.com/115981550/218143557-26ec33ce-99a7-4db6-a46f-1cf48ed77ae0.png)

### **Task 2: Setting up an Application Load Balancer (ALB)**

1. **Create an Application Load Balancer:**
    
    * Navigate to the EC2 Dashboard and select "Load Balancers."
        
    * Click on "Create Load Balancer."
        
    * Choose "Application Load Balancer" and configure it.
        
    * Add listener (e.g., HTTP on port 80).
        
    * Configure security settings and create a new security group.
        
    * Review and create the ALB.
        
2. **Configure Target Groups:**
    
    * While creating the ALB, create a new target group or use an existing one.
        
    * Configure health checks and target registration settings.
        
3. **Add EC2 Instances to the ALB:**
    
    * In the ALB dashboard, go to the "Target Groups" tab.
        
    * Click on the target group you created.
        
    * Under "Targets," click "Edit" and add the two EC2 instances.
        
4. **Verify ALB Functionality:**
    
    * In the ALB dashboard, go to the "Description" tab to find the DNS name of your ALB.
        
    * Open a web browser and navigate to the ALB DNS name.
        
    * You should see the same webpage as before, but now the requests are being load-balanced between the two instances.
        
5. **Check Health Status:**
    
    * In the ALB dashboard, go to the "Target Groups" tab.
        
    * Select the target group and check the health status of your instances.
        

# ***How to create Application Load Balancer***

* *To create a application load balancer, go to the EC2 console* [*https://console.aws.amazon.com/ec2/v2/home and in the left-hand menu under Load B*](https://console.aws.amazon.com/ec2/v2/home)*a*[*lancing, click on Load Balancers.*](https://console.aws.amazon.com/ec2/v2/home)
    

![](https://miro.medium.com/v2/resize:fit:875/1*SEuuFedWjZP2R8nI2TY00g.png align="left")

1. [*Gi*](https://console.aws.amazon.com/ec2/v2/home)*ve your Load balancer some meaningful name e.g., my-alb-demo*
    
2. *You need to select Scheme(it can be Internet-facing(An internet-facing load b*[*alancer routes requests from clients over*](https://console.aws.amazon.com/ec2/v2/home) *the internet to targets.* [*Requires a public subnet) or Internal(An*](https://console.aws.amazon.com/ec2/v2/home) *internal load balancer routes requests from clients to targets using private IP addresses))*
    
3. *IP address type(Can be IPv4 or Dualstack(Includes IPv4 and IPv6 addresses))*
    

![](https://miro.medium.com/v2/resize:fit:875/1*DkWomnWsGUTvfz8ZMghvzA.png align="left")

* *Select the VPC and availability zone*
    

![](https://miro.medium.com/v2/resize:fit:875/1*E3MO0qqU4IHbeyVCISBeGA.png align="left")

* *Under Listeners an*[*d routing, define the port and protocol on*](https://console.aws.amazon.com/ec2/v2/home) *which the load balancer must listen. Ea*[*ch Application*](https://console.aws.amazon.com/ec2/v2/home)
    
* [*Load Balancer needs at l*](https://console.aws.amazon.com/ec2/v2/home)*e*[*ast one listener to accept traffic.*](https://console.aws.amazon.com/ec2/v2/home)
    

![](https://miro.medium.com/v2/resize:fit:875/1*5Wsq9zoK9QrHzR1jHAhlDw.jpeg align="left")

* *Click on the Target group. Target group defines the logical grouping of the* [*targets.*](https://console.aws.amazon.com/ec2/v2/home)
    

![](https://miro.medium.com/v2/resize:fit:875/1*s01kOULRS_jkKo2gZFoTiw.png align="left")

![](https://miro.medium.com/v2/resize:fit:875/1*W4rkCwZODy1z6yJJx_DUbg.png align="left")

![](https://miro.medium.com/v2/resize:fit:875/1*W4rkCwZODy1z6yJJx_DUbg.png align="left")

* [*Click on Next at the bott*](https://console.aws.amazon.com/ec2/v2/home)*om of the screen*
    

![](https://miro.medium.com/v2/resize:fit:875/1*nh8X23maS9csS4A5-kI3RQ.jpeg align="left")

* *Cl*[*ick on Create target group*](https://console.aws.amazon.com/ec2/v2/home)
    

![](https://miro.medium.com/v2/resize:fit:875/1*3Witt8B-4YxbZPTpo75aeA.png align="left")

* [*Go back t*](https://console.aws.amazon.com/ec2/v2/home)*o the ALB console and select the target group you h*[*ave just created. Click on Create load bal*](https://console.aws.amazon.com/ec2/v2/home)*ancer* [*at the bottom of the screen.*](https://console.aws.amazon.com/ec2/v2/home)
    

![](https://miro.medium.com/v2/resize:fit:875/1*3Witt8B-4YxbZPTpo75aeA.png align="left")

[That's it! You've just completed the task. �](https://console.aws.amazon.com/ec2/v2/home)�

Thank you so much for taking the time to read till the end! Hope you found this blog informative and helpful.

Feel free to explore more of my content, and don't hesitate to reach out if need any assistance from me or in case of you have any questions.

Happy Learning!