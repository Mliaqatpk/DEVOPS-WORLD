---
title: "Day 23 - 90daysofdevops: Jenkins Freestyle Project for DevOps Engineers."
datePublished: Thu Dec 21 2023 05:08:11 GMT+0000 (Coordinated Universal Time)
cuid: clqeqs19h000008lbbe3e3a7x
slug: day-23-90daysofdevops-jenkins-freestyle-project-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703135205718/03ec42d3-48e6-40e0-8e63-629b0c4c4232.png
tags: aws, learning, cloud-computing, jenkins, learning-journey, 90daysofdevops, trainwithshubham, tws

---

CI/CD stands for Continuous Integration and Continuous Deployment (or Continuous Delivery). It's a set of practices and principles in software development aimed at improving the development process, making it more efficient, reliable, and automated. Let's break down each part:

1. **Continuous Integration (CI):**
    
    * **Integration:** Developers frequently merge their code changes into a shared repository (version control system, like Git). This helps to catch integration issues early on.
        
    * **Automated Builds:** With each integration, an automated build and a series of tests are triggered to ensure that the code integrates correctly and does not introduce new bugs or conflicts.
        
2. **Continuous Deployment (CD):**
    
    * **Continuous Delivery:** The software is kept in a state where it could be deployed to production at any time. This involves automated testing and builds to ensure that the software is always in a deployable state.
        
    * **Continuous Deployment:** Changes that pass the automated tests and other quality checks are automatically deployed to production environments without manual intervention.
        

The primary goals of CI/CD are to:

* **Detect and Fix Issues Early:** By integrating code frequently and running automated tests, issues are identified and fixed as soon as possible, reducing the chances of bugs accumulating over time.
    
* **Streamline Development:** Automation of the build and deployment processes reduces manual effort, making the development and release cycles more efficient.
    
* **Increase Confidence in Code Quality:** The automated testing and deployment processes provide a level of confidence in the stability and reliability of the codebase.
    
* **Facilitate Collaboration:** CI/CD encourages collaboration among development and operations teams by providing a standardized and automated process.
    

## What Is a Build Job?

A build job is an automated process that compiles, tests, and packages software code. It is a fundamental element of continuous integration and continuous delivery (CICD) pipelines, enabling developers to build and test their code frequently and reliably.

**Key Characteristics of a Build Job:**

1. **Automation:** Build jobs are automated, meaning they run without manual intervention. This automation ensures consistency and efficiency in the build process, reducing the risk of human error.
    
2. **Code Compilation:** Build jobs compile source code into a machine-readable format, such as an executable file or bytecode. This compilation process transforms the human-readable code into a form that can be executed by the computer.
    
3. **Code Testing:** Build jobs typically include unit tests, integration tests, and other types of automated testing to ensure that the code is functioning correctly and meeting the desired requirements.
    
4. **Code Packaging:** Build jobs often package the compiled code into a distributable format, such as a package or container image. This packaging facilitates easy deployment of the software to different environments.
    
5. **Triggered by Code Changes:** Build jobs are typically triggered whenever there are changes to the source code. This ensures that the code is always tested and built after any modifications, preventing potential issues from going undetected.
    

**Types of Build Jobs:**

1. **Full Build:** A full build compiles and tests the entire codebase, providing a comprehensive assessment of the software's health.
    
2. **Incremental Build:** An incremental build only compiles and tests the changed portions of the codebase, focusing on the updated code and reducing build time.
    
3. **Release Build:** A release build produces a final, deployable version of the software that is ready for distribution to users.
    
4. **Integration Build:** An integration build verifies that different components of the software integrate correctly, ensuring that the overall system functions as intended.
    

---

## Task-01

* create a agent for your app. ( which you deployed from docker in earlier task)
    
* Create a new Jenkins freestyle project for your app.
    
* In the "Build" section of the project, add a build step to run the "docker build" command to build the image for the container.
    
* Add a second step to run the "docker run" command to start a container using the image created in step 3.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703135003142/00ef360a-555a-4401-829b-449b4cefc45b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703135019297/3809d355-ab59-47be-bc39-4d7083d4caeb.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703135032162/8f54a9ee-7c6a-4b8a-9ec0-b52d57e49aa9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703135045085/cdde2e9d-4723-405b-a0df-6cb3980a7b86.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703135072553/30dbdf4f-3013-4b31-a142-b133a2620910.png align="center")

## if Permission related error come follow below steps:

permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "[http://%2Fvar%2Frun%2Fdocker.sock/v1.24/build?buildargs=%7B%7D&](http://%2Fvar%2Frun%2Fdocker.sock/v1.24/build?buildargs=%7B%7D&amp;) Like this .

**Add User to Docker Group:** Add your user to the docker group, which should have the necessary permissions to access the Docker daemon socket. Run the following command:

```plaintext
sudo usermod -aG docker $USER
```

* After running this command, you may need to log out and log back in, or restart your system for the changes to take effect.
    
* **Check Docker Daemon Socket Permissions:** Verify the permissions of the Docker daemon socket file. Run:
    

```plaintext
ls -l /var/run/docker.sock 
```

* **Restart Docker:** After making any changes, restart the Docker service to apply the changes:
    

```plaintext
sudo service docker restart

reboot 
```

The produced image and container are visible.