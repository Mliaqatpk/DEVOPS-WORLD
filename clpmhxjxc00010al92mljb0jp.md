---
title: "𝐷𝑎𝑦 16: 𝐷𝑜𝑐𝑘𝑒𝑟 𝑀𝑎𝑑𝑒 𝐸𝑎𝑠𝑦: 𝑆𝑡𝑟𝑒𝑎𝑚𝑙𝑖𝑛𝑖𝑛𝑔 𝐷𝑒𝑣𝑂𝑝𝑠 𝑓𝑜𝑟 𝐸𝑓𝑓𝑜𝑟𝑡𝑙𝑒𝑠𝑠 𝐴𝑝𝑝 𝐷𝑒𝑝𝑙𝑜𝑦𝑚𝑒𝑛𝑡"
datePublished: Fri Dec 01 2023 10:42:59 GMT+0000 (Coordinated Universal Time)
cuid: clpmhxjxc00010al92mljb0jp
slug: 16
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701427258177/0833b79d-2206-4be9-a1c1-6643f52e1c98.png
tags: docker, learning, learn-coding, learning-journey, shubhamlondhe, trainwithshubham, tws

---

### **🔶 Understanding Docker**

Docker stands out as a remarkable software platform designed to facilitate the swift development, testing, and deployment of applications. It achieves this by encapsulating software into standardized units known as containers. These containers encompass all essential elements for software execution, such as libraries, system tools, code, and runtime. Docker provides a versatile solution for deploying and scaling applications across diverse environments, ensuring the seamless functioning of your code.

Having already installed Docker in previous tasks, let's delve into executing Docker commands to further enhance our understanding and utilization.

🔶 Task-1: Running a Container with 'docker run'

Initiate a new container and interact with it via the command line using the 'docker run' command. Example: 'docker run hello-world.'

```plaintext
docker run hello-world
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701426364603/1a00ded1-745f-4b26-b054-9a67a8401616.png align="center")

🔶 Task-2: Examining Container or Image Details with 'docker inspect'

Utilize the 'docker inspect' command to gain in-depth information about a container or image.

```plaintext
docker inspect hello-world
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701426434225/7736d157-d585-49a7-b490-9cded1e7b19a.png align="center")

🔶 Task-3: Managing Port Mappings with 'docker port'

List port mappings for a container using the 'docker port' command.

```plaintext
docker run -d -p 80:80 nginx
docker port webserver
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701426845027/04c3902d-7f2d-47f8-85e8-bbb6e4e15432.png align="center")

🔶 Task-4: Monitoring Resource Usage with 'docker stats'

Obtain resource usage statistics for one or more containers through the 'docker stats' command.

```plaintext
docker stats webserver
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701426907572/1e981a9d-df73-4957-8059-55344a613c57.png align="center")

🔶 Task-5: Viewing Processes with 'docker top'

Use the 'docker top' command to observe the processes running inside a container.

```plaintext
docker top webserver
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701426974021/8ac53037-adf8-41c4-a4ab-6ea1e6da9b21.png align="center")

🔶 Task-6: Archiving Images with 'docker save'

Save an image to a tar archive using the 'docker save' command.

```plaintext
docker save -o nginx_image.tar nginx
ls -lh nginx_image.tar
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701427136534/ca371570-6304-4268-9b78-6334aa312d66.png align="center")

🔶 Task-7: Loading Images from Archive with 'docker load'

Load an image from a tar archive using the 'docker load' command.

```plaintext
docker load -i nginx_image.tar
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701427163956/0e945fa2-5372-4fd3-b2fc-9d0e1c3ceef8.png align="center")

These tasks involve straightforward operations crucial for managing images and containers effectively.

In conclusion, Docker has emerged as a transformative tool for DevOps engineers, revolutionizing software development, testing, and deployment practices. Its containerization technology encapsulates applications and their dependencies, ensuring consistency across various environments and eliminating the "it works on my machine" issue.

DevOps engineers leverage Docker to streamline the development-to-production pipeline, fostering collaboration, accelerating delivery, and improving software quality. The capability to package applications into portable containers facilitates seamless deployment on any infrastructure, from local development machines to cloud servers.