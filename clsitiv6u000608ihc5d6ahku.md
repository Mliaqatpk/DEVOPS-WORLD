---
title: "Day 43 S3 Programmatic access with AWS-CLI 💻 📁"
datePublished: Mon Feb 12 2024 10:55:31 GMT+0000 (Coordinated Universal Time)
cuid: clsitiv6u000608ihc5d6ahku
slug: day-43-s3-programmatic-access-with-aws-cli
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jLwVAUtLOAQ/upload/1cbf81ba061464d846fe5931577d7b53.jpeg
tags: cloud, aws, cloud-computing, automation, jenkins, cloud-native, 90daysofdevops, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, batch-5

---

Day 43 of *#90daysofdevops*

In today's tech landscape, mastering cloud storage solutions like Amazon S3 (Simple Storage Service) is akin to wielding a powerful tool in the arsenal of any developer, data scientist, or IT professional. Amazon S3 offers a highly scalable, reliable, and secure infrastructure for storing and retrieving data. However, to truly harness its potential, one must delve deeper into its capabilities, including programmatic access facilitated by the AWS Command Line Interface (CLI).

### **Understanding Programmatic Access**

Programmatic access to Amazon S3 refers to interacting with S3 resources using scripts, commands, or programming languages rather than through the web-based management console. This approach offers several advantages, including automation, scalability, and integration with existing workflows or applications.

### **Introducing AWS CLI**

The AWS CLI is a unified tool for managing AWS services through the command line. It provides a comprehensive interface to interact with various AWS services, including S3, EC2, Lambda, and more. Leveraging the AWS CLI for S3 operations allows users to streamline tasks, automate processes, and integrate S3 functionalities into their workflows seamlessly.

### **Getting Started with AWS CLI and S3**

To begin harnessing the power of programmatic access with AWS CLI and S3, one must first set up the AWS CLI and configure it with appropriate credentials. This involves installing the AWS CLI, configuring access keys, and specifying the default region.

Once set up, users can execute various commands to perform tasks such as creating buckets, uploading/downloading objects, setting permissions, and managing storage classes. For example, to list the contents of an S3 bucket, one can use the `aws s3 ls s3://bucket-name` command, while uploading a file can be accomplished with `aws s3 cp file.txt s3://bucket-name`.

### **Advantages of Programmatic Access with AWS CLI**

1. **Automation**: By scripting S3 operations, repetitive tasks can be automated, saving time and reducing the risk of human error.
    
2. **Scalability**: Programmatic access allows for the rapid scaling of S3 operations, catering to dynamic workloads and resource demands.
    
3. **Integration**: S3 functionality can be seamlessly integrated into existing applications, workflows, or CI/CD pipelines using the AWS CLI.
    
4. **Flexibility**: Users have granular control over S3 operations, enabling customization and optimization based on specific requirements.
    
5. **Efficiency**: With a command-line interface, users can execute S3 tasks quickly and efficiently, without the need for manual intervention.
    

### **Best Practices and Considerations**

While programmatic access with AWS CLI offers immense benefits, it's essential to adhere to best practices and consider security implications. This includes implementing least privilege access, encrypting sensitive data, monitoring and logging S3 activities, and regularly reviewing access policies.

Additionally, users should stay informed about updates, new features, and best practices related to AWS services and CLI commands to optimize their workflows continually.

### S3

Amazon Simple Storage Service (Amazon S3) is an object storage service that provides a secure and scalable way to store and access data on the cloud. It is designed for storing any kind of data, such as text files, images, videos, backups, and more.

In this blog post, we will explore how to leverage AWS Command Line Interface (AWS CLI) for programmatic access to S3. We'll cover two tasks that involve launching an EC2 instance, creating an S3 bucket, uploading and accessing files, creating EC2 snapshots, and downloading files from S3 using the AWS CLI.

### Task-01

* Launch an EC2 instance using the AWS Management Console and connect to it using Secure Shell (SSH).
    
* Create an S3 bucket and upload a file to it using the AWS Management Console.
    
* Access the file from the EC2 instance using the AWS Command Line Interface (AWS CLI).
    

### Step 1: Launch an EC2 Instance

1. Log in to the AWS Management Console.
    
2. Navigate to the EC2 service.
    
3. Click on "Launch Instance" and follow the wizard to configure your EC2 instance.
    
4. Download the key pair and launch the instance.
    

### Step 2: Connect to the EC2 Instance

1. Open a terminal window.
    
2. Use the downloaded key pair to SSH into the EC2 instance:
    

```plaintext
ssh -i path/to/keypair.pem ec2-user@<your-instance-ip>
```

### Step 3: Create an S3 Bucket and Upload a File

1. In the AWS Management Console, go to the S3 service.
    
2. Click "Create Bucket" and follow the prompts to create a bucket.
    
3. Upload a file to the bucket.
    

### **Step 4: Access the File from the EC2 Instance using AWS CLI**

1. Install AWS CLI on the EC2 instance:
    

You can check the previous blog for the AWS CLI installation

1. Configure AWS CLI with your credentials:
    

```plaintext
aws configure
```

1. Use the following command to copy the file from S3 to the EC2 instance:
    

```plaintext
aws s3 cp s3://your-bucket-name/your-file.txt /path/on/ec2/instance/
```

### Task-02: Creating EC2 Snapshots and Downloading from S3

### **Step 1: Create a Snapshot of the EC2 Instance**

1. In the AWS Management Console, navigate to the EC2 service.
    
2. Right-click on your running instance, select "Create Image," and follow the prompts to create a snapshot.
    

### Step 2: Launch a New EC2 Instance from the Snapshot

1. In the AMIs section of the EC2 service, launch a new instance using the created snapshot.
    

### Step 3: Download a File from S3 Using AWS CLI

1. On the new EC2 instance, install and configure AWS CLI as in Task-01.
    
2. Use the following command to download the file from S3:
    

```plaintext
aws s3 cp s3://your-bucket-name/your-file.txt /path/on/ec2/instance/
```

### **Step 4: Verify Contents on Both EC2 Instances**

1. Compare the contents of the file on both EC2 instances:
    

```plaintext
diff /path/on/first/ec2/instance/your-file.txt /path/on/second/ec2/instance/your-file.txt
```

This command will show no output if the files are identical.

That's it! You've just completed the task. 🎉

Thank you so much for taking the time to read till the end! Hope you found this blog informative and helpful.

Feel free to explore more of my content, and don't hesitate to reach out if need any assistance from me or in case of you have any questions.

Happy Learning!