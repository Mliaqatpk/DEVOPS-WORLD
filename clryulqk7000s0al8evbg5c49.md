---
title: "Day 38 & 39 Getting Started with AWS Basics☁"
datePublished: Mon Jan 29 2024 11:30:21 GMT+0000 (Coordinated Universal Time)
cuid: clryulqk7000s0al8evbg5c49
slug: day-38-39-getting-started-with-aws-basics
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706523014232/46d9a60c-b761-4844-9446-edc47272fbbd.png
tags: cloud, aws, cloud-computing, automation, jenkins, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, tws, 90, batch5

---

![Top AWS Services](https://allcode.com/wp-content/uploads/2021/02/Group-169-3.png align="left")

Hey Techies! Welcome to this blog

In this blog, we are Getting Started with AWS Basics☁

In this, we'll guide you through hands-on tasks to master Identity and Access Management (IAM), launch EC2 instances, set up Jenkins, and deploy Docker. Whether you're a beginner or looking to enhance your AWS skills, follow these step-by-step instructions for a comprehensive understanding.

To empower an IAM (Identity and Access Management) user for EC2 (Elastic Compute Cloud) access in AWS (Amazon Web Services), you need to follow these general steps. Please note that you should have the necessary permissions in your AWS account to perform these actions.

### **Step 1: Sign in to the AWS Management Console**

Log in to the AWS Management Console using your administrator credentials.

### **Step 2: Navigate to IAM**

1. In the AWS Management Console, go to the "Services" menu and select "IAM" under the "Security, Identity, & Compliance" section.
    

### **Step 3: Create a New IAM User**

1. In the IAM dashboard, click on "Users" in the left navigation pane.
    
2. Click on the "Add user" button.
    
3. Enter a username for the new IAM user.
    
4. Select the type of access for the user. For EC2 access, you might want to select "Programmatic access" and/or "AWS Management Console access" based on your use case.
    
5. Set up the user's permissions. You can either add the user to an existing group with the required EC2 permissions or attach policies directly to the user. Ensure that the user has at least the necessary permissions for EC2, such as `AmazonEC2FullAccess` or a custom policy that includes the required permissions.
    
6. Optionally, you can add tags to the user for better organization.
    
7. Review your choices and click on the "Create user" button.
    

### **Step 4: Download or Copy Security Credentials**

1. After creating the user, you will be prompted to download the security credentials (Access key ID and Secret access key). Ensure that you save these credentials securely, as they will be needed to authenticate the IAM user.
    

### **Step 5: Configure AWS CLI or SDK**

If you selected "Programmatic access" in step 3, you'll need to configure the AWS Command Line Interface (CLI) or an SDK with the IAM user's credentials:

1. Install the AWS CLI if you haven't already.
    
2. Run `aws configure` and provide the Access Key ID, Secret Access Key, region, and output format when prompted.
    

### **Step 6: Test EC2 Access**

1. Use the configured credentials to run AWS CLI commands or use SDKs to interact with EC2 resources. For example, you can run `aws ec2 describe-instances` to list existing instances.
    

Step 1: Create an IAM User with EC2 Access

1. Navigate to the AWS Management Console.
    
2. Open the IAM dashboard and click on "Users."
    
3. Click "Add user," enter a username, and select "Programmatic access."
    
4. Attach the "AmazonEC2FullAccess" policy.
    
5. Review and create the user, noting the access key and secret key.
    

Step 2: Launch a Linux EC2 Instance with Jenkins and Docker

Create a Shell Script for Docker, e.g., [`docker.sh`](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html):

```plaintext
#!/bin/bash

# install docker

sudo apt-get update
sudo apt install docker.io

# give permission
sudo usermod -aG docker $USER
```

For Jenkins,

```plaintext
#!/bin/bash

# install jenkins

# First install java before jenkins

sudo apt update
sudo apt install fontconfig openjdk-17-jre

# Install jenkins

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

Make the script executable and run it:

```plaintext
chmod +x docker.sh jenkins.sh
./docker.sh
./jenkins.sh
```

This scripts installs Jenkins and Docker on your EC2 instance.

### Task 2: Assembling Your DevOps Avengers

Step 1: Create DevOps IAM Users

1. Head to the IAM dashboard.
    
2. Create three users: DevOpsUser1, DevOpsUser2, and DevOpsUser3.
    
3. Attach policies such as "AmazonEC2FullAccess" to each user.
    

Step 2: Group Users into DevOps Groups

1. In the IAM dashboard, navigate to "Groups."
    
2. Create a group named "DevOpsGroup."
    
3. Add the three DevOps users to this group.
    

### Task 3: Launching Jenkins on EC2

Step 1: Launch an EC2 Instance with Jenkins

1. Go to the EC2 dashboard.
    
2. Launch an instance with Amazon Linux 2 AMI.
    
3. In the user data section, add:
    

```plaintext
#!/bin/bash

# install jenkins

# First install java before jenkins

sudo apt update
sudo apt install fontconfig openjdk-17-jre

# Install jenkins

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

sudo systemctl start jenkins
```

Complete the instance creation process.

Step 2: Access Jenkins Page

1. Once the instance is running, note its public IP address.
    
2. In your browser, enter `http://<your-instance-ip>:8080`.
    
3. Retrieve the Jenkins initial password from the instance:
    

```plaintext
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Follow the on-screen instructions to set up Jenkins.

### **Task 4: Unraveling IAM Roles**

Step 1: Understand IAM Roles

Before creating IAM roles, let's delve into the concept of IAM Roles. IAM Roles are AWS Identity and Access Management entities that define a set of permissions for making AWS service requests. Unlike IAM users, roles do not have any credentials; instead, they rely on temporary security tokens.

Roles are useful in scenarios such as cross-account access, temporary access for users or applications, and delegating permissions to AWS services.

Read more about IAM Roles [**here**](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html).

Step 2: Create IAM Roles

1. In the IAM dashboard, navigate to "Roles."
    
2. Create three roles: DevOps-User, Test-User, and Admin.
    
3. Define the respective policies for each role.
    

That's it! You've just completed the task. 🎉

Thank you so much for taking the time to read till the end! Hope you found this blog informative and helpful.

Feel free to explore more of my content, and don't hesitate to reach out if need any assistance from me or in case of you have any questions.