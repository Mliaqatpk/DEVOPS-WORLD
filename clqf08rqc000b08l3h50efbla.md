---
title: "🙂 𝙳𝚊𝚢 𝟸𝟻 𝚃𝚊𝚜𝚔 - 𝟿𝟶𝚍𝚊𝚢𝚜𝚘𝚏𝚍𝚎𝚟𝚘𝚙𝚜: 𝙲𝚘𝚖𝚙𝚕𝚎𝚝𝚎 𝙹𝚎𝚗𝚔𝚒𝚗𝚜 𝙲𝙸/𝙲𝙳 𝙿𝚛𝚘𝚓𝚎𝚌𝚝 - 𝙳𝚘𝚌𝚞𝚖𝚎𝚗𝚝𝚊𝚝𝚒𝚘𝚗 🙂"
datePublished: Thu Dec 21 2023 09:33:08 GMT+0000 (Coordinated Universal Time)
cuid: clqf08rqc000b08l3h50efbla
slug: 8jzgidwnzmz8j2aivcdmqig8j2fupcdn7sg8j2agcdmorwnzqc8j2alcatipcdn7wnz28j2ajfcdmorwnzqi8j2anpcdmpjwnzqp8j2ajfcdmo7wnzqf8j2ampcdmpnwnzqcoidwnzmy8j2ampcdmpbwnzqz8j2alfcdmo7wnzqd8j2ajidwnzm58j2ajvcdmpfwnzqu8j2akvcdmpfwnzqcipcdmblwnzm4lcdmblwnzmzipcdmbwnzqb8j2ampcdmppwnzqo8j2ajpcdmp0glsdwnzmz8j2ampcdmozwnzqe8j2alvcdmo7wnzqx8j2anfcdmorwnzqd8j2akvcdmpjwnzqxipcfmyi
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703151047696/e9cca63a-2f30-4c54-9e95-1714ac99e198.png
tags: aws, web-development, jenkins, jenkins-devops, 90daysofdevops, shubhamlondhe, trainwithshubham, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, tws

---

![](https://miro.medium.com/v2/resize:fit:1358/1*yOGabRyBdOz3xBlWvN56SQ.jpeg align="left")

## Task-01: README Documentation for CI/CD Pipeline

## Project Title: Node.js CI/CD Pipeline with Docker, Java, and Jenkins

## Overview:

**This project sets up a continuous integration and continuous deployment (CI/CD) pipeline for a Node.js application using Docker, Java, and Jenkins on an AWS EC2 instance. Follow the steps below to replicate the setup.**

### Steps:

1. **Launch an EC2 Instance:**Launch an EC2 instance on AWS with an Amazon Linux 2 AMI / Ubuntu.
    
2. **Connect to EC2 Instance:**Connect to your EC2 instance using SSH.
    
3. **Install Docker:**bash
    

* sudo yum update -y sudo apt-get install docker sudo service docker start sudo usermod -a -G docker ec2-user
    
* **Install Java:**bash
    
* sudo yum install java-1.8.0-openjdk -y
    
* **Install Jenkins:**Download and install Jenkins from the [official Jenkins website](https://jenkins.io/download/).Access Jenkins dashboard in your web browser.
    
* **Create Jenkins Job:**Create a new job, name it, and select "Pipeline" as the job [type.In](https://jenkins.io/download/) the job configuration, select "Pipeline script" and paste the provided script.
    
* **Configure GitHub Webhook:**Save the job and go to its configuration page.Under "Build triggers," select "GitHub hook trigger for GITScm polling."
    
* **Create GitHub Webhook:**In your GitHub repository settings, navigate to "Webhooks" and create a new webhook.Set the payload URL to http://&lt;jenkins-host&gt;:&lt;jenkins-port&gt;/GitHub-webhook/.
    
* **Create Docker Compose** [**File:**Create](https://jenkins.io/download/) a docker-compose.yml file in the project root with the provided content.yaml
    

1. **version: '3.9' services: web: build: . ports: - "8000:8000"**
    
2. **Commit and Trigger Pipeline:**Commit changes to your GitHub repository and wait for Jenkins to trigger the pipeline automatically.
    
3. **Access Deployed Application:**Once the pipeline completes successfully, your application should be accessible at http://&lt;publicip&gt;:8000/.
    

### Conclusion:

### Congratulations! You have successfully set up a CI/CD pipeline for your Node.js application.

  
Task-02: Goal Setting

## Goal: To Become a DevOps Engineer

### Strategies:

1. **Develop a Strong Foundation in Software Development:**Learn programming languages (e.g., Python, Java).Understand version control systems (e.g., Git,GitHub,Git Lab).
    
2. **Gain Expertise in Automation Tools and Technologies:**Learn and practice automation tools (e.g., Ansible, Puppet, Chef).Master containerization and orchestration tools (e.g., Docker, Kubernetes).
    
3. **Learn About Cloud Computing:**Gain proficiency in cloud platforms (e.g., AWS, Azure).Understand infrastructure as code (IaC) principles.
    
4. **Focus on Collaboration and Communication:**Enhance teamwork and communication skills.Understand the importance of cross-functional collaboration.
    
5. **Stay Current with Industry Trends:**Follow industry blogs, forums, and attend conferences.Stay updated on emerging technologies and practices in DevOps.
    
6. **Practice Continuous Learning:**Engage in ongoing learning through courses and certifications.Regularly explore new tools and methodologies in DevOps.
    

### Note to Self:

Continuous learning is key; stay consistent and never give up on the journey towards becoming a DevOps engineer.

### Result:

### ᴀᴄʜɪᴇᴠɪɴɢ ᴛʜᴇ ɢᴏᴀʟ ᴏꜰ ʙᴇᴄᴏᴍɪɴɢ ᴀ ᴅᴇᴠᴏᴘꜱ ᴇɴɢɪɴᴇᴇʀ ᴛʜʀᴏᴜɢʜ ᴅᴇᴅɪᴄᴀᴛɪᴏɴ ᴀɴᴅ ᴄᴏɴᴛɪɴᴜᴏᴜꜱ ɪᴍᴘʀᴏᴠᴇᴍᴇɴᴛ.