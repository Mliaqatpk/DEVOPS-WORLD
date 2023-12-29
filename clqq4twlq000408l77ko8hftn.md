---
title: "Day26 - 90DaysOfDevOps Jenkins Declarative Pipeline"
datePublished: Fri Dec 29 2023 04:27:01 GMT+0000 (Coordinated Universal Time)
cuid: clqq4twlq000408l77ko8hftn
slug: day26-90daysofdevops-jenkins-declarative-pipeline
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703823950278/cc0bfc96-5151-4e6f-a6ea-d02c461ebd2d.png
tags: aws, cloud-computing, automation, jenkins, ci-cd, jenkins-devops, 90daysofdevops, trainwithshubham

---

### What is pipeline?

The pipeline is a series of steps or stages that software code passes through, with each stage serving a specific purpose in the software development lifecycle. The goal of a pipeline is to automate and streamline the process of building, testing, and deploying software, reducing manual intervention and improving efficiency.

### What Scripted vs Declarative pipeline in Jenkins?

Jenkins Pipeline provides two distinct approaches for defining and executing automated tasks: scripted and declarative pipelines.

**Scripted Pipeline**

Scripted pipelines are the original and more flexible approach to Jenkins Pipeline. They allow for writing arbitrary Groovy code within the pipeline script, granting complete control over the execution flow.

Key characteristics of scripted pipelines:

* Utilizes Groovy language for defining pipeline steps and logic
    
* Offers maximum control over the execution flow
    
* Can be quite complex and difficult to maintain
    

```plaintext
node {
    checkout scm
    sh 'mvn clean install'
    sh 'mvn test'
}
```

**Declarative Pipeline**

Declarative pipelines introduce a more structured and declarative way of defining pipeline stages, tasks, and parameters. They utilize a more human-readable syntax and break down complex processes into manageable stages.

Key characteristics of declarative pipelines:

* Employs a declarative syntax for defining pipeline stages and tasks
    
* Offers a more readable and maintainable structure
    
* Well-suited for standard software development workflows
    

```plaintext
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
```

### What is agent in Jenkins?

Agent in Jenkins is an remote machine or container that executes the tasks specified in a Jenkins pipeline. Agents are responsible for doing the actual work of building, testing, and deploying software.

There are two main types of agents in Jenkins:

* **Self-hosted agents:** These agents are installed and managed locally on a specific machine. They are typically used for continuous integration (CI) jobs, where the code is constantly being built and tested.
    
* **Remote agents:** These agents are hosted on remote machines or cloud instances. They are typically used for continuous delivery (CD) jobs, where the code is automatically deployed to production.
    

In addition to these two main types, there are also several other types of agents, such as:

* **Docker agents:** These agents use Docker containers to execute tasks. This allows for a more consistent and portable environment, as the tasks are isolated from the host machine.
    
* **Kubernetes agents:** These agents use Kubernetes clusters to execute tasks. This can be a more scalable and efficient solution for large-scale deployments.
    
* **Slave agents:** These are older-style agents that are no longer recommended for use. They are not as flexible or scalable as self-hosted or remote agents.
    

---

## Task-01

* Create a New Job, this time select Pipeline instead of Freestyle Project.
    
* Follow the Official Jenkins [Hello world example](https://www.jenkins.io/doc/pipeline/tour/hello-world/)
    
* Complete the example using the Declarative pipeline
    

\==&gt;

Login to Jenkins : [http://localhost:8080](https://www.jenkins.io/doc/pipeline/tour/hello-world/) OR [http://publicipaddress:8080](https://www.jenkins.io/doc/pipeline/tour/hello-world/)

Then select (NEW\_ITEM) create Jenkins declarative pipeline.

![](https://media.licdn.com/dms/image/D4D12AQGEUrfTv1Adlg/article-inline_image-shrink_1500_2232/0/1701265491269?e=1709164800&v=beta&t=OSB1yzgOEQViKG63Pkjr-0W7QKun4U1kRelnQ6k5Cj4 align="left")

Give the name of declarative pipeline and select (PIPELINE) from Jenkins dashboard.

![](https://media.licdn.com/dms/image/D4D12AQGisKJ11XTJgg/article-inline_image-shrink_1500_2232/0/1701265618776?e=1709164800&v=beta&t=CKXFCxcW6OM3t5owTiCyCQrjrRoE3eehaaJ8f2ztQJE align="left")

In (GENERAL) give some description about your pipeline !!

![](https://media.licdn.com/dms/image/D4D12AQExrvpy1YN-cg/article-inline_image-shrink_1500_2232/0/1701265789578?e=1709164800&v=beta&t=G98kk798MABYiS0rwQQ1VWYgZbiFP38wPdckNrVc5O0 align="left")

select (PIPELINE) then write your first pipeline !!!

then (APPLY) and (SAVE) changes !!

![](https://media.licdn.com/dms/image/D4D12AQEpr06WbsNj7Q/article-inline_image-shrink_1500_2232/0/1701265941337?e=1709164800&v=beta&t=FpOG5JZRaMnhm7tetmVoZDlQ869TXiLUDHIgqd-Uf0Y align="left")

![](https://media.licdn.com/dms/image/D4D12AQGnRDTXYRP93A/article-inline_image-shrink_1500_2232/0/1701266106972?e=1709164800&v=beta&t=2oxSBiOkrZLtb4KlH8nmLJDWRToqROyy0aVv7NXq-iU align="left")

Then click (BUILD NOW) , it will build your pipeline !!!!!

go to (CONSOLE OUTPUT) to check your script processes and finished status.

![](https://media.licdn.com/dms/image/D4D12AQGvkKfZhabXug/article-inline_image-shrink_1500_2232/0/1701266185870?e=1709164800&v=beta&t=ZvwIfVP1SG51ncsNG7vjSyjwY0YZZUFUysf9S_THwLo align="left")

---

### Hope this article will prove to be valuable, helping you to understand Jenkins .