---
title: "Day 27 Task: Jenkins Declarative Pipeline with Docker"
datePublished: Fri Dec 29 2023 10:16:25 GMT+0000 (Coordinated Universal Time)
cuid: clqqhb8ql000008l69okv3irk
slug: day-27-task-jenkins-declarative-pipeline-with-docker
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703844326145/e15cb5e4-826f-4294-9eec-be764f33a19d.png
tags: automation, jenkins, jenkins-devops, jenkinswhat-is-jenkinsjenkins-tutorialjenkins-tutorial-for-beginnersjenkins-pipelinejenkins-pipeline-tutorialjenkins-trainingkarl-jenkinsjenkins-full-courselearn-jenkinsintroduction-to-jenkinsjenkins-ciwhat-is-jenkins-and-how-it-worksjenkins-crash-coursejenkins-continuous-integration-tutorialjenkins-ci-cd-pipelinejenkins-for-beginnerscontinuous-integration-jenkinshow-jenkins-build-workswhat-is-jenkins-in-devopsjenkins-course

---

🚀 **Mastering CI/CD with Jenkins Declarative Pipeline and Docker** 🐳💻

Ready to supercharge your Continuous Integration and Deployment process? Let's explore the seamless integration of Jenkins Declarative Pipeline with Docker, a match made in DevOps heaven! 🚀🔧

### **1\. Docker in the Pipeline: The Power Duo**

* **Containerization Magic:** Leverage Docker containers for consistent and reproducible builds, ensuring your application runs smoothly across different environments.
    
* **Isolation Benefits:** Ensure a clean and isolated environment for each stage of your pipeline, preventing dependency conflicts and guaranteeing reliability.
    

### **2\. Declarative Pipeline Syntax: Simplify, Clarify, Optimize**

* **Human-Readable Code:** Craft cleaner and more readable pipeline code using the Declarative Pipeline syntax, reducing complexity and making maintenance a breeze.
    
* **Structured Steps:** Define stages, steps, and post-actions effortlessly, providing a clear and concise structure to your CI/CD process.
    

### **3\. Seamless Integration Steps: A Quick How-To**

* **Agent Configuration:** Set up your pipeline to run on a Docker-enabled agent, ensuring compatibility and scalability.
    
* **Docker Commands:** Use Docker commands within your pipeline stages to build, tag, and push images seamlessly.
    
* **Artifact Management:** Employ Docker for artifact management, simplifying the storage and retrieval of application artifacts.
    

### **4\. Parallelism and Efficiency: The Docker Advantage**

* **Parallel Execution:** Leverage Docker's lightweight nature to parallelize tasks, optimizing build and deployment times for faster results.
    
* **Resource Efficiency:** Docker's resource efficiency allows for running multiple builds concurrently, reducing overall pipeline execution time.
    

### **5\. Version Control and Dockerfiles: Best Practices**

* **Versioning Images:** Implement best practices for versioning Docker images, ensuring traceability and rollback options.
    
* **Optimized Dockerfiles:** Craft efficient Dockerfiles to create minimalistic images, improving build speed and reducing resource consumption.
    

# **Docker Build and Run**

docker build — you can use `sh 'docker build . -t <tag>'` in your pipeline stage block to run the docker build command. (Make sure you have docker installed with correct permissions.

docker run: you can use `sh 'docker run -d <image>'` in your pipeline stage block to build the container.

How will the stages look

```plaintext
stages {
        stage('Build') {
            steps {
                sh 'docker build -t trainwithshubham/django-app:latest'
            }
        }
    }
```

# **Task-01**

* Create a docker-integrated Jenkins declarative pipeline
    
* Use the above-given syntax using `sh` inside the stage block
    
* You will face errors in case of running a job twice, as the docker container will be already created, so for that do task 2.
    

### **Step 1: Create a New Pipeline Job**

* Open Jenkins and navigate to the dashboard.
    
* Click on "New Item" to create a new pipeline job.
    

### Step 2: Configure Your Pipeline Script

* In the job configuration, scroll down to the "Pipeline" section.
    
* Choose "Pipeline script" from the Definition dropdown.
    
* In the script box, enter the following:
    

**COPY**

**COPY**

```plaintext
pipeline {
    agent any
    stages {
        stage("Code"){
            steps{
                git url: "https://github.com/Mliaqatpk/node-todo-cicd", branch:"master"
                echo "Code Clone"
            }
        }
        stage("Build & Test"){
            steps{
                sh "docker build -t node-app:latest ."
                echo "Code Build & Test"
            }
        }
        stage("Scan"){
            steps{
                echo "Code scan completed !!!"
            }
        }
        stage("Run"){
            steps{
                sh "docker run -d -p 8000:8000 node-app"
                echo "Run Completed"
            }
        }
    }
}
```

### **Save and Run Your Job**

* Save your configuration.
    
* Run your Jenkins job.
    
* Check whether the application is working on port 8000 or not.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703843968916/78a28ae7-1707-4a33-b522-62306b455259.png align="center")

  

### **Task-02**

* Create a docker-integrated Jenkins declarative pipeline using the `docker` groovy syntax inside the stage block.
    

### **Update Your Pipeline Script**

* Open the configuration of the same job you created for Task-01.
    
* Update the script box with the following:
    

```plaintext
pipeline {
    agent any
    stages {
        stage("Code"){
            steps{
                git url: "https://github.com/Mliaqatpk/node-todo-cicd", branch:"master"
                echo "Code Clone"
            }
        }
        stage("Build & Test"){
            steps{
                sh "docker build -t node-app:latest ."
                echo "Code Build & Test"
            }
        }
        stage("Scan"){
            steps{
                echo "Code scan completed !!!"
            }
        }
        stage("Push"){
            steps{
                withCredentials([usernamePassword(credentialsId:"dockerHub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]) {
                    sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                    sh " docker tag node-app:latest ${env.dockerHubUser}/node-app:latest"
                    sh " docker push ${env.dockerHubUser}/node-app:latest"
                    echo "Code pushed to the DockerHub"
                }
            }
        }
        stage("Deploy"){
            steps{
            sh "docker-compose down"
            sh " docker-compose up -d"
            }
        }
    }
}
```

### **Save and Run Your Job**

* Save your configuration.
    
* Run your Jenkins job again.
    

  

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844137498/8d25eb83-c4e6-4609-9009-6d1373af96e9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844148894/8b867b82-5fc9-499f-9186-be14f7944025.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844158651/802b5b40-60b4-496f-9756-894915ca8cda.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844167402/e5c5a37d-6540-42dc-af8b-40a19b431956.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844172293/e7a89f24-7989-405a-b28d-884d55550b61.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844179735/f761fb3e-691a-4db3-a26a-14384522a2b3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844186199/182c4018-cf6d-4bb0-ad5a-a8331e56f5f9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844193343/1983527b-04aa-45a9-803a-814cd737c413.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844205032/52c556c3-d807-4001-a4d0-48148b325d60.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703844212391/82791f38-2789-420b-914b-8645d4ea5628.png align="center")