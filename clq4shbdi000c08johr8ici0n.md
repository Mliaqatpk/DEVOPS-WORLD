---
title: "Day 19 Task: Docker for DevOps Engineers"
datePublished: Thu Dec 14 2023 05:58:08 GMT+0000 (Coordinated Universal Time)
cuid: clq4shbdi000c08johr8ici0n
slug: day-19-task-docker-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702533370723/bc7e150b-5023-43f8-85a9-202598f8797a.png
tags: cloud, docker, developer, cloud-computing, devops, docker-compose, docker-images, devops-articles, docker-volume, shubhamlondhe, trainwithshubham

---

# Docker-Volume

🚀 Elevate Your Docker Game with Volumes: Unleashing the Power of Data Persistence 🚀

Hey Dev Enthusiasts! 🚀✨

Let's dive into the heart of Docker magic – Volumes! 🐳💾

In the ever-evolving world of containerization, Docker has proven itself as the maestro orchestrator. And what fuels this symphony of seamless deployment, scalability, and isolation? None other than the unsung hero – Docker Volumes! 🦸‍♂️🎶

🌌 **Beyond the Container Walls: Persistent Data Nirvana**

Volumes are like the secret passage to a world beyond the container walls – a dimension where data isn't ephemeral, but everlasting. No more tears over lost data when containers bid adieu. With Docker Volumes, your data is like a phoenix, rising from the ashes every time you spin up a container. 🔥📦

💡 **Why Volumes, You Ask?**

1. **Data Survivability:** Volumes ensure your data survives the container lifecycle. Say goodbye to data loss; say hello to resilience! 🌐
    
2. **Collaboration in Style:** Volumes facilitate collaboration between containers. It's like a VIP lounge where containers can sip on data without stepping on each other's toes. 🥂👯‍♂️
    
3. **Upgrade without Anxiety:** When you need to upgrade or change your container, worry not! Volumes keep your precious data intact, allowing you to morph your application without losing sleep. 😴💻
    

🎩 **Mastering the Art of Volume Management**

Creating volumes is a breeze – just a simple command, and voila! But, don't be fooled by simplicity; the real magic lies in understanding how to wield this power. Docker Compose, anyone? 🎭📜

```plaintext
docker volume create my_volume
```

And when you're orchestrating with Docker Compose:

```plaintext
services:
  my_app:
    image: my_image
    volumes:
      - my_volume:/app/data
```

It's like poetry in code – elegance and functionality hand in hand! 🤝💻

🔥 **Pro Tips for Volume Virtuosos**

1. **Named Volumes for Glory:** Give your volumes a name, like naming a star in the coding cosmos. It's not just organized; it's classy! 🌟💼
    

```plaintext
docker volume create --name my_precious_volume
```

1. **Volume Mounting Mastery:** Mount volumes like a pro. Map host directories to container paths – a seamless bridge between worlds. 🌉🗺️
    

```plaintext
docker run -v /host/path:/container/path my_image
```

🌈 **Conclusion: Where Data Dreams Come True**

In the realm of containerization, Docker Volumes are the guardians of your data, ensuring it thrives beyond the ephemeral dance of containers. Embrace the power, understand the syntax, and watch your applications soar to new heights!

# Docker Network

In the ever-evolving landscape of containerization, Docker has emerged as a revolutionary tool, streamlining the deployment and management of applications across diverse environments. One of the key features that propels Docker's efficiency is its robust networking capabilities. In this blog post, we will embark on a journey through the intricacies of Docker networking, exploring its concepts, types, and best practices.

Understanding Docker Networking:

Docker networking enables communication between containers and external networks, ensuring seamless data flow and connectivity. It facilitates the creation of isolated environments, allowing containers to communicate with each other or external systems while maintaining security and efficiency.

### **Core Concepts:**

1. **Bridge Networks:**
    
    Docker employs a default bridge network named `bridge` for communication between containers on the same host. Containers connected to this bridge can communicate effortlessly using internal IP addresses. However, external access typically requires port mapping.
    
    ```plaintext
    docker network create my_bridge_network
    docker run --network=my_bridge_network -d my_container
    ```
    
2. **Host Networks:**
    
    Containers using the host network share the network namespace with the Docker host, eliminating network isolation. This configuration can enhance performance but sacrifices some degree of security.
    
    ```plaintext
    docker run --network=host -d my_container
    ```
    
3. **Overlay Networks:**
    
    Overlay networks facilitate communication between containers running on different hosts. Docker Swarm, Docker's native clustering and orchestration solution, often leverages overlay networks for seamless cross-host communication.
    
    ```plaintext
    docker network create --driver=overlay my_overlay_network
    ```
    
4. **Macvlan Networks:**
    
    Macvlan networks allow containers to appear as separate physical devices on the network. This is useful when containers need direct access to external networks without Network Address Translation (NAT).
    
    ```plaintext
    docker network create -d macvlan --subnet=192.168.1.0/24 --gateway=192.168.1.1 -o parent=eth0 my_macvlan_network
    ```
    

### **Docker Compose and Networking:**

[Docker Compose](https://docs.docker.com/compose/) simplifies multi-container applications by defining services, networks, and volumes in a YAML file. When dealing with complex applications, Docker Compose provides an elegant solution for managing networking configurations.

Example `docker-compose.yml`:

```plaintext
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
    networks:
      - my_network

networks:
  my_network:
    driver: bridge
```

### **Best Practices:**

1. **Use User-Defined Networks:**
    
    Creating user-defined networks provides better control over container communication. It enables custom naming, better isolation, and simplified management.
    
2. **Leverage DNS for Service Discovery:**
    
    Docker automatically provides DNS resolution for container names within the same user-defined network. Utilize this feature for seamless service discovery.
    
3. **Consider Network Security:**
    
    Employ firewalls, network policies, and container-specific security measures to enhance network security. Limiting unnecessary exposure of ports and communication channels is crucial.
    
4. **Monitor and Troubleshoot:**
    
    Docker provides commands like `docker network ls` and `docker network inspect` for monitoring and troubleshooting network configurations. Regularly audit your network settings to ensure optimal performance.
    

## Tasks

## Task-1

* Create a multi-container docker-compose file which will bring *UP* and bring *DOWN* containers in a single shot ( Example - Create application and database container )
    

*hints:*

* Use the `docker-compose up` command with the `-d` flag to start a multi-container application in detached mode.
    
* Use the `docker-compose scale` command to increase or decrease the number of replicas for a specific service. You can also add [`replicas`](https://stackoverflow.com/questions/63408708/how-to-scale-from-within-docker-compose-file) in deployment file for *auto-scaling*.
    
* Use the `docker-compose ps` command to view the status of all containers, and `docker-compose logs` to view the logs of a specific service.
    
* Use the `docker-compose down` command to stop and remove all containers, networks, and volumes associated with the application
    

## Task-2

* Learn how to use Docker Volumes and Named Volumes to share files and directories between multiple containers.
    
* Create two or more containers that read and write data to the same volume using the `docker run --mount` command.
    
* Verify that the data is the same in all containers by using the docker exec command to run commands inside each container.
    
* Use the docker volume ls command to list all volumes and docker volume rm command to remove the volume when you're done.
    

![](https://4032318958-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-M1neGLLQ0sDXeK6ooSo%2Fuploads%2Fgit-blob-c33e6a5de3b1fd0f6881556455e4f888347600eb%2F1-architecture-voting-app.png?alt=media align="left")

Our codebase will comprise three services that will be containerized and managed by a `docker-compose` file. Additionally, we will use Postgres as a database and Redis as a message broker to offload some of the computational load to the `worker` service. Our services will be:

* **Vote:** A frontend and some server-side code that will push the vote made by a user to Redis. This will be built in Python, using the Flask framework.
    
* **Result:** A frontend that uses a websocket API to poll data from its server-side implementation to provide real-time updates of votes. This will be a Node.js application that uses Express to serve an Angular frontend. The frontend will use [Socket.IO](http://socket.io/) to manage the websocket connection.
    
* **Worker:** The background task processor that reads from Redis and creates entries in our Postgres database to represent the results of the votes. The worker will be implemented using Java
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702533108672/cecc9abc-72e0-4371-8bba-a7cf7c5615f9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702533111219/00d957a6-e184-426d-a7dc-5553baa4fb0d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702533115138/2ae16093-3d8f-4fad-be7a-a005f5ff5453.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702533122474/36e052ab-6d6a-44fd-a6fc-131a1dcd370a.png align="center")

```plaintext
version: "3"

services:
  vote:
    build: ./vote
    command:
      - python
      - app.py
    ports:
      - "5000:80"
    depends_on:
      - "redis"
      - "db"
  
  result:
    build: ./result
    command:
      - nodemon
      - server.js
    ports:
      - "5001:80"
    depends_on:
      - "redis"
      - "db"
  
  worker:
    build:
      context: ./worker
    depends_on:
      - "redis"
      - "db"
  
  redis:
    image: redis:alpine
    ports:
      - "6379"
    volumes:
      - redis:/data
  
  db:
    image: postgres:14
    ports:
      - "5432"
    volumes:
      - postgres-data:/var/lib/postgresql/data
    environment:
      POSTGRES_PASSWORD: postgres
      POSTGRES_USER: postgres

volumes:
  postgres-data: {}
  redis: {}
```