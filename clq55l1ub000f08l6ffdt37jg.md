---
title: "Day 21 Task: Docker Important interview Questions."
datePublished: Thu Dec 14 2023 12:04:57 GMT+0000 (Coordinated Universal Time)
cuid: clq55l1ub000f08l6ffdt37jg
slug: day-21-task-docker-important-interview-questions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702555388352/fa7852e3-67ec-4b40-86e0-77bb0abb4748.png
tags: docker, aws, devops, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, tws

---

**What is the Difference between an Image, Container and Engine?**

**Image:**

An image is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools.

**container**

A container is a runtime instance of a Docker image, or more generally, a lightweight, standalone, and executable software package that includes everything needed to run a piece of software, including the code and runtime.

The engine refers to the container runtime, which is responsible for running containers on a host system

an image is a packaged application and its dependencies, a container is a running instance of that image, and the engine is the runtime environment responsible for creating and managing containers on a host system

**What is the Difference between the Docker command COPY vs ADD?**

COPY is a docker file command that copies files from a local source location to a destination in the Docker container. It only has only one assigned function.

Its role is to duplicate files/directories in a specified location in their existing format.

ADD command is used to copy files/directories into a Docker image.

It can also copy files from a URL.

ADD command is used to download an external file and copy it to the wanted destination.

**What is the Difference between the Docker command CMD vs RUN?**

RUN executes commands and creates new image layers.

CMD sets the command and its parameters to be executed by default after the container is started.

RUN - command triggers while we build the docker image.

CMD - command triggers while we launch the created docker image.

**How Will you reduce the size of the Docker image?**

USE A SMALLER BASE IMAGE

DON’T INSTALL DEBUG TOOLS LIKE curl/vim/nano

MINIMIZE LAYERS

**Why and when to use Docker?**

Using Docker, you can quickly deploy and scale applications into any environment and know your code will run

Why use Docker:

Portability:

Docker containers encapsulate everything an application needs to run, including the code, runtime, libraries, and dependencies. This makes it easy to move applications between different environments, such as development, testing, and production.

Consistency:

Docker provides consistency across different development and deployment environments. Since containers run the same way everywhere, you can avoid the classic "it works on my machine" problem.

Isolation:

Containers provide process isolation, ensuring that each application and its dependencies run in its own isolated environment. This isolation helps prevent conflicts between different applications and allows for a more predictable and stable runtime.

Resource Efficiency:

Docker containers share the host OS kernel, making them more lightweight than traditional virtual machines. This results in better resource utilization and faster startup times.

Scalability:

Docker makes it easy to scale applications horizontally by running multiple instances of containers. This is particularly useful for microservices architectures where different components of an application can be independently scaled.

Versioning and Rollback:

Docker allows you to version your container images. This makes it easy to roll back to a previous version if there are issues with a new release.

Continuous Integration and Deployment (CI/CD):

Docker is commonly used in CI/CD pipelines, facilitating automated testing and deployment processes. Containers can be easily integrated into various CI/CD tools, streamlining the software development lifecycle.

When to use Docker:

Multi-Platform Development:

When developing applications that need to run consistently across different operating systems, Docker provides a solution by encapsulating dependencies within containers.

Microservices Architecture:

Docker is well-suited for deploying applications built on a microservices architecture. Each microservice can run in its own container, enabling independent development, scaling, and deployment.

DevOps Practices:

In a DevOps environment, Docker can streamline collaboration between development and operations teams. It promotes the concept of "Infrastructure as Code" and helps in building and deploying applications more efficiently.

Legacy Application Migration:

Docker can be used to containerize legacy applications, allowing them to run on modern infrastructure without major code changes.

Cloud Migration:

When migrating applications to the cloud, Docker containers offer a consistent environment across different cloud providers and on-premises infrastructure.

Resource Optimization:

When you want to optimize resource usage and have more efficient utilization of server resources, Docker containers provide a lightweight alternative to traditional virtualization.

In summary, Docker is beneficial when you need consistency, portability, and scalability for your applications. It is particularly useful in modern development practices, such as microservices architecture and continuous integration/deployment pipelines.

**Explain the Docker components and how they interact with each other.**

Docker consists of several components that work together to enable the creation, deployment, and management of containerized applications. Here are the main components and their interactions:

Docker Daemon:

The Docker Daemon is a background process that manages Docker containers on a host system. It listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes.

Docker Client:

The Docker Client is a command-line interface (CLI) tool that allows users to interact with the Docker Daemon. It sends commands to the Docker Daemon using the Docker API. Users can use the Docker CLI to build, run, and manage containers on the host system.

Docker Images:

Docker Images are lightweight, standalone, and executable packages that include everything needed to run a piece of software, including the code, runtime, libraries, and system tools. Images are created from a set of instructions called a Dockerfile, and they serve as the basis for creating Docker containers.

Docker Containers:

Containers are instances of Docker images that run as isolated processes on the host system. Containers encapsulate an application and its dependencies, providing consistency and portability across different environments. Multiple containers can run on the same host, each isolated from the others.

Docker Registry:

Docker Registry is a repository for storing and sharing Docker images. Docker Hub is the default public registry, but organizations often set up private registries for storing proprietary or sensitive images. Users can push (upload) and pull (download) images from a registry.

Docker Compose:

Docker Compose is a tool for defining and running multi-container Docker applications. It uses a YAML file to configure the services, networks, and volumes required for the application. With a single command, Docker Compose can start and manage multiple containers as a single application.

Docker Volumes:

Docker Volumes provide a way to persist data generated by and used by Docker containers. Volumes can be mounted into containers, allowing data to be stored outside the container and survive container restarts or removals.

Docker Network:

Docker Networks allow containers to communicate with each other and with the outside world. Docker provides default networks, and users can create custom networks for more complex configurations. Containers on the same network can communicate with each other using container names as hostnames.

Here's how these components interact:

The Docker Daemon runs in the background, managing containers and responding to requests from the Docker Client.

Users interact with the Docker Daemon using the Docker CLI (Client).

Docker Images are built from Dockerfiles and stored in Docker Registries.

Docker Containers are instances of Docker Images, running as isolated processes on the host system.

Docker Compose can be used to define and manage multi-container applications.

Docker Volumes provide persistent storage for containers.

Docker Networks enable communication between containers.

**Explain the terminology: Docker Compose, Docker File, Docker Image, Docker Container?**

Docker Compose:

Docker Compose is a tool that allows you to define and run multi-container Docker applications. It uses a YAML file to specify the services, networks, and volumes for an application and then starts and manages the containers as a single unit. Docker Compose simplifies the process of running complex, interconnected applications by defining their configuration in a single file.

Dockerfile:

A Dockerfile is a text document that contains a set of instructions for building a Docker image. It defines the base image, sets up the environment, and specifies the commands to run to install dependencies and configure the application. The Dockerfile is used as input to the docker build command, resulting in the creation of a Docker image.

Docker Image:

A Docker image is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools. Images are created from a set of instructions defined in a Dockerfile. Images can be stored in Docker Registries and shared with others, making it easy to distribute and deploy applications consistently across different environments.

Docker Container:

A Docker container is a running instance of a Docker image. Containers are isolated environments that encapsulate an application and its dependencies. They run as lightweight, portable, and executable units on the host system. Containers can be started, stopped, and managed independently of each other. They provide consistency across different environments, making it easier to develop, test, and deploy applications.

In summary:

Docker Compose is a tool for defining and managing multi-container applications.

A Dockerfile is a set of instructions for building a Docker image.

A Docker image is a lightweight, standalone, and executable package that includes everything needed to run a piece of software.

A Docker container is a running instance of a Docker image, providing a lightweight and isolated environment for applications.

**In what real scenarios have you used Docker?**

Containerization and deployment of web applications

Microservices architecture

Continuous integration and deployment (CI/CD) pipelines

Testing and development environments

Cloud computing and serverless computing

Big data and machine learning applications

Desktop virtualization and remote workstations.

1. ### **Docker vs Hypervisor?**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681533530994/745febee-4e3f-4b47-b7eb-42abaa185b10.png?auto=compress,format&format=webp align="left")
    
    Here's a brief comparison of Docker and hypervisors:
    
    * Docker operates at the application level, while hypervisors operate at the operating system level.
        
    * Docker containers are smaller and more lightweight than virtual machines created by hypervisors.
        
    * Docker containers share the same host operating system, while virtual machines created by hypervisors each have their own separate operating system.
        
    * Docker is designed for use in a microservices architecture, while hypervisors are more commonly used in monolithic applications.
        
    

1. ### **What are the advantages and disadvantages of using docker?**
    
    Here are the advantages and disadvantages of using Docker in short:
    
    **Advantages:**
    
    * Portability: Docker allows you to package applications and dependencies into portable containers that can be run on any machine that supports Docker, regardless of the underlying operating system.
        
    * Consistency: Docker ensures that the environment in which an application runs is consistent across different development, testing, and production environments, reducing the risk of runtime errors due to inconsistencies.
        
    * Isolation: Docker containers provide a high degree of isolation between applications, which reduces the risk of conflicts between applications and improves security.
        
    * Efficiency: Docker containers are lightweight and consume fewer resources than traditional virtual machines, which reduces the costs associated with running and scaling applications.
        
    

**Disadvantages:**

* Complexity: Docker adds an additional layer of complexity to application deployment, which can increase the learning curve for developers and operations teams.
    
* Security: Docker containers can be vulnerable to security risks if they are not properly configured and managed.
    
* Persistence: By default, Docker containers are designed to be ephemeral, which means that any data or changes made within the container will be lost when the container is stopped or deleted. This requires additional configuration to ensure data persistence.
    
* Performance: Although Docker containers are lightweight, they can still introduce a performance overhead compared to running applications natively on the host operating system.
    

1. ### What is a Docker namespace?
    
    In short, a Docker namespace is a way to isolate resources (such as processes, network interfaces, and file systems) between containers and the host system. Docker namespaces allow multiple containers to run on the same host without interfering with each other or with the host system. Each Docker namespace creates a unique view of a particular resource, so that it appears to the container as if it has its own isolated copy of that resource, while in reality it is sharing the same underlying resource with other containers. There are several types of namespaces used by Docker, including the PID namespace for isolating process IDs, the network namespace for isolating network interfaces, and the mount namespace for isolating file systems.
    
2. ### **What is a Docker registry?**
    
    Docker registry is a central location where Docker images are stored and distributed. It is similar to a code repository, but instead of containing source code, it contains Docker images that can be used to run applications. Docker registries can be public or private, and can be used to store images for use within an organization or to share images with the wider community. The most commonly used public Docker registry is Docker Hub, which allows users to store and share Docker images, and also provides an easy way to search for and download images created by other users. Private Docker registries can also be set up within an organization to store and distribute custom images that are not publicly available.
    
3. ### What is an entry point?
    
    An entry point in Docker is a command that is executed when a container is started from an image. It can be thought of as the default command that runs when a container is started and is specified in the Dockerfile using the `ENTRYPOINT` directive. The entry point can be useful for setting up the container environment or for starting a specific process or application. It can be overridden by passing a command to the `docker run` command.
    
4. ### **How to implement CI/CD in Docker?**
    
    * Set up a version control system (VCS) such as Git and create a repository for your project.
        
    * Create a Dockerfile that defines the environment and dependencies needed to run your application.
        
    * Use a CI/CD tool such as Jenkins or GitLab CI/CD to automate the build process for your Docker image. The CI/CD tool can be configured to trigger a build when changes are pushed to the VCS repository.
        
    * Push the built Docker image to a Docker registry such as Docker Hub or a private registry.
        
    * Use an orchestration tool such as Kubernetes or Docker Compose to deploy the Docker container to a production environment.
        
    * Use a continuous monitoring and testing tool to ensure that the deployed application is running smoothly and any issues are detected and resolved quickly.
        
    

By implementing CI/CD in Docker, you can streamline the development and deployment process, reduce errors, and ensure that your application is running reliably and efficiently.

1. ### **Will data on the container be lost when the docker container exits?**
    
    In short, data on a Docker container will be lost when the container exits if the data is stored only in the container's writable layer. This is because the container's writable layer is a temporary file system that is created when the container is started and is deleted when the container exits.
    
    To persist data across container restarts, you can use Docker volumes or bind mounts. Docker volumes allow data to be stored outside the container's writable layer, while bind mounts allow a directory on the host system to be mounted into the container.
    
    By using volumes or bind mounts, data can be stored independently of the container and can be reused across container restarts or even across multiple containers. This can be useful for storing configuration files, application data, or databases.
    
2. ### **What is a Docker swarm?**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681535156596/2532712c-7339-40e8-824c-603b577b6f5e.png?auto=compress,format&format=webp align="left")
    
    Docker swarm is a clustering and orchestration tool that allows you to manage multiple Docker hosts as a single virtual system. It provides features for scaling, load balancing, service discovery, and high availability, making it easy to deploy and manage containers across multiple hosts.
    
3. What are the docker commands for the following:
    

* **view running containers**
    
    ```plaintext
      docker ps
    ```
    
* **command to run the container under a specific name**
    

* ```plaintext
      docker run -td --name <container_name> <image_name> /bin/bash
    ```
    
* command to export a docker
    
    ```plaintext
      docker export <container-name-or-id> > container.tar
    ```
    
    This will export the contents of the container to a file called `container.tar` in your current directory.
    
    Note that `docker export` does not include the container's metadata, such as its name, entry point, or command. It only exports the contents of the container's file system.
    
    To export a Docker image as a tar archive, you can use the `docker save` command followed by the name or ID of the image and redirect the output to a file. For example:
    
    ```plaintext
      docker save <image-name-or-id> > image.tar
    ```
    
    This will save the image as a tar archive called `image.tar` in your current directory.
    
* **command to import an already existing docker image**
    
    ```plaintext
      docker load < image.tar
      docker pull <image-name>
    ```
    
* **commands to delete a container**
    
    ```plaintext
      docker rm <container_id>
    ```
    
* **command to remove all stopped containers, unused networks, build caches, and dangling images?**
    
    ```plaintext
      docker system prune -a
    ```
    

* **What are the common docker practices to reduce the size of Docker Image?**
    
    Here are some common Docker practices to reduce the size of Docker images:
    
    * Use a smaller base image: Instead of using a large base image such as Ubuntu or CentOS, use a smaller base image such as Alpine Linux, which is designed to be small and lightweight.
        
    * Minimize the number of layers: Each command in a Dockerfile creates a new layer in the image. Minimizing the number of layers reduces the image size and speeds up the build process.
        
    * Use multi-stage builds: Multi-stage builds allow you to use multiple Dockerfiles in a single build, resulting in smaller and more efficient images.
        
    * Use .dockerignore: The .dockerignore file allows you to specify files or directories that should be excluded from the build context. This reduces the amount of data sent to the Docker daemon and improves build performance.
        
    * Remove unnecessary files: Make sure to remove any unnecessary files or packages from your image, as they can significantly increase the size of the image.
        
    * Use Docker image layers efficiently: Make sure to order the instructions in the Dockerfile in such a way that Docker can take advantage of image layers. For example, place instructions that are unlikely to change at the top of the Dockerfile.
        

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*Thank You\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*