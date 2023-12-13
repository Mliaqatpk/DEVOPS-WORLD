---
title: "ᴅᴀʏ 18 ᴛᴀꜱᴋ: ᴅᴏᴄᴋᴇʀ ꜰᴏʀ ᴅᴇᴠᴏᴘꜱ ᴇɴɢɪɴᴇᴇʀꜱ"
datePublished: Wed Dec 13 2023 05:43:24 GMT+0000 (Coordinated Universal Time)
cuid: clq3ciirp000608ky38kpaana
slug: 18
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702446130909/41732690-b342-4fa3-8020-1b4adead3f86.png
tags: docker, aws, docker-compose, 90daysofdevops, trainwithshubham, tws

---

## Docker Compose

* Docker Compose is a tool that was developed to help define and share multi-container applications.
    
* With Compose, we can create a YAML file to define the services and with a single command, can spin everything up or tear it all down.
    
* Learn more about docker-compose [visit here](https://tecadmin.net/tutorial/docker/docker-compose/)
    

## What is YAML?

* YAML is a data serialization language that is often used for writing configuration files. Depending on whom you ask, YAML stands for yet another markup language or YAML ain’t markup language (a recursive acronym), which emphasizes that YAML is for data, not documents.
    
* YAML is a popular programming language because it is human-readable and easy to understand.
    
* YAML files use a .yml or .yaml extension.
    
* Read more about it [here](https://www.redhat.com/en/topics/automation/what-is-yaml)
    

## Task-1

Learn how to use the docker-compose.yml file, to set up the environment, configure the services and links between different containers, and also to use environment variables in the docker-compose.yml file.

[Sample docker-compose.yaml file](https://github.com/LondheShubham153/90DaysOfDevOps/blob/master/2023/day18/docker-compose.yaml)

## Task-2

* Pull a pre-existing Docker image from a public repository (e.g. Docker Hub) and run it on your local machine. Run the container as a non-root user (Hint- Use `usermod` command to give user permission to docker). Make sure you reboot instance after giving permission to user.
    
* Inspect the container's running processes and exposed ports using the docker inspect command.
    
* Use the docker logs command to view the container's log output.
    
* Use the docker stop and docker start commands to stop and start the container.
    
* Use the docker rm command to remove the container when you're done.
    

## How to run Docker commands without sudo?

* Make sure docker is installed and system is updated (This is already been completed as a part of previous tasks):
    
* sudo usermod -a -G docker $USER
    
* Reboot the machine.
    

  
Title: Unleashing the Power of Docker Compose: Simplifying Container Orchestration

---

Docker Compose is a game-changer in the world of containerization, offering a streamlined approach to managing multi-container Docker applications. Whether you're a seasoned developer or just getting started with container orchestration, Docker Compose is a tool that can significantly simplify your workflow.

**What is Docker Compose?**

Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to define a multi-container Docker application in a single file, then spin up your entire application stack with a single command. This not only streamlines the deployment process but also ensures that your development, testing, and production environments are consistent.

**Key Features:**

1. **Declarative Configuration:** With Docker Compose, you describe your application's services, networks, and volumes in a `docker-compose.yml` file. This file serves as a blueprint for your entire application stack, making it easy to version control and share with others.
    
2. **Effortless Scaling:** Need to scale your application services? Docker Compose makes it a breeze. With a simple command, you can scale services up or down to meet the demands of your application, ensuring optimal performance.
    
3. **Service Dependencies:** Docker Compose allows you to define dependencies between services, ensuring that services start up in the correct order. This eliminates the need for complex startup scripts and guarantees that your application components are ready to interact.
    
4. **Environment Variables and Overrides:** Customize your application's configuration without modifying the `docker-compose.yml` file. Docker Compose supports environment variables and override files, giving you flexibility without sacrificing simplicity.
    
5. **Network Isolation:** Each Docker Compose project gets its own isolated network by default, preventing conflicts with other projects on the same host. This ensures that your applications are running in an isolated environment, reducing potential security risks.
    

**Getting Started:**

1. Install Docker Compose: If you haven't already, install Docker Compose by following the instructions provided on the official [Docker Compose Installation Guide](https://docs.docker.com/compose/install/).
    
2. Create a `docker-compose.yml` file: Define your services, networks, and volumes in a YAML file. This file serves as the blueprint for your application stack.
    
3. Run your application: With a single command (`docker-compose up`), launch your entire application stack. Docker Compose takes care of pulling the necessary images, creating containers, and connecting everything together.
    
4. Explore additional commands: Docker Compose offers a range of commands to manage your containers, networks, and volumes. Explore commands like `docker-compose ps`, `docker-compose down`, and `docker-compose scale` to enhance your container orchestration experience.
    

**Conclusion:**

Docker Compose simplifies the complexities of managing multi-container Docker applications, offering a user-friendly solution for developers, sysadmins, and DevOps professionals. Its declarative configuration, scalability features, and ease of use make it an invaluable tool in the containerization toolkit.

Embrace the power of Docker Compose, and unlock a more efficient and streamlined approach to orchestrating your containerized applications. Happy containerizing! 🐳✨

## What is YAML?

YAML, pronounced as "YAML" or sometimes "YAML Ain't Markup Language," is a human-readable data serialization format. It is often used for configuration files and data exchange between languages with different data structures. YAML's syntax is designed to be easily readable by humans, and it uses indentation to represent the structure of data.

**Key Characteristics of YAML:**

1. **Human-Readable:** One of YAML's main strengths is its readability. The syntax is clean and intuitive, using indentation to represent the hierarchical structure of data. This makes it easy for both humans and machines to parse and understand.
    
2. **Whitespace Matters:** Unlike some other data formats, YAML relies on indentation (whitespace) to define the structure. Consistent indentation is crucial for the correct interpretation of the data.
    
3. **Data Types:** YAML supports a variety of data types, including scalars (strings, numbers, and booleans), sequences (arrays or lists), and mappings (key-value pairs or dictionaries). This flexibility makes YAML suitable for a wide range of use cases.
    
4. **Comments:** YAML allows comments, denoted by the '#' symbol. Comments can be useful for adding context or explanations within the configuration files.
    
5. **No Complicated Symbols:** YAML avoids the use of complex symbols like braces or brackets to denote structures, making it simpler and more approachable for users.
    

**Basic YAML Syntax:**

```plaintext
 Example YAML Document
person:
  name: John Doe
  age: 30
  hobbies:
    - Reading
    - Hiking
  address:
    city: Anytown
    country: USA
```

In this example, we have a YAML document representing information about a person. The indentation indicates the hierarchy, with the person having attributes like name, age, hobbies, and address.

**Use Cases for YAML:**

1. **Configuration Files:** Many software applications use YAML for configuration files. Whether it's setting up a web server, configuring a build pipeline, or defining application settings, YAML provides a concise and human-readable format.
    
2. **Data Serialization:** YAML is commonly used to serialize data between different programming languages. Its simplicity and readability make it a preferred choice for data exchange formats.
    
3. **Infrastructure as Code (IaC):** YAML is prevalent in the world of Infrastructure as Code tools like Ansible, Kubernetes, and Docker Compose. It allows users to define complex infrastructure configurations in a straightforward manner.
    
4. **Application Configuration:** Frameworks and libraries often use YAML for defining settings and options. This makes it easy for developers to customize the behavior of their applications without delving into complex code changes.
    

  
Using a `docker-compose.yml` file allows you to define and manage multi-container Docker applications, configure services, set up environment variables, and establish links between containers. Below is a guide on how to achieve these tasks.

**1\. Setting Up the Environment:**

Create a `docker-compose.yml` file in the root of your project. Define the services, networks, and volumes your application requires. Here's a simple example for a web application with a frontend and a backend:

```plaintext
version: '3'

services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
  backend:
    image: your-backend-image:latest
    ports:
      - "8000:8000"
```

In this example, we have two services: `web` for an Nginx web server and `backend` for your backend application.

**2\. Configuring Services:**

You can configure each service with various options. For example, specifying environment variables, setting up volumes, or defining dependencies. Here's an extended version of the previous example:

```plaintext
version: '3'

services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
    volumes:
      - ./web:/usr/share/nginx/html
  backend:
    image: your-backend-image:latest
    ports:
      - "8000:8000"
    environment:
      - DATABASE_URL=postgres://user:password@postgres:5432/db
    depends_on:
      - postgres
  postgres:
    image: postgres:latest
    environment:
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=password
      - POSTGRES_DB=db
```

Here, we added a `volumes` section for the `web` service, specifying a local directory to be mounted into the Nginx container. We also added an `environment` section for the `backend` service, defining a database connection URL, and introduced a `depends_on` section to ensure the `backend` service starts only after the `postgres` service.

**3\. Establishing Links Between Containers:**

In modern versions of Docker Compose (version 3 and above), service-to-service communication is achieved through the service names defined in the `docker-compose.yml` file. In the example above, the `backend` service communicates with the `postgres` service using the hostname `postgres`. This works because they are part of the same network.

**4\. Using Environment Variables:**

Environment variables in `docker-compose.yml` are specified under the `environment` key for each service. You can define specific variables or load them from an external file using the `env_file` option. Here's an example:

```plaintext
version: '3'

services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
    environment:
      - DEBUG=true
  backend:
    image: your-backend-image:latest
    ports:
      - "8000:8000"
    env_file:
      - ./backend/.env
```

In this example, the `DEBUG` environment variable is set for the `web` service directly in the `docker-compose.yml` file, while the `backend` service loads environment variables from a file named `.env` located in the `backend` directory.

**5\. Running the Docker Compose:**

Navigate to the directory containing your `docker-compose.yml` file and run:

```plaintext
docker-compose up
```

This command will start the defined services based on the configurations in your `docker-compose.yml` file. Use `docker-compose down` to stop and remove the containers.

By following these steps, you can effectively use a `docker-compose.yml` file to set up and configure your multi-container Docker environment, establish communication between services, and leverage environment variables for configuration.

## Task-2

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702445994782/ec1de2c7-9c81-4e90-b97e-608f289b91d5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702445999701/e3a75f26-ace5-4195-b704-f1f6acb1588f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702446003593/88114eb2-d1dc-4e9c-9586-3042294d9926.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702446009356/2409c246-1088-4fce-b784-507ce09ef6cc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702446013301/62ca92e5-34fd-4869-80f4-64ad45ec2759.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702446018039/05765392-60d3-46eb-88d8-57ec939087f6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702446021218/89233e09-51a0-4679-a71c-8bd8560b9eb5.png align="center")

```plaintext
version: "3.9"
services:
  # Database
  db:
    image: mysql:5.7
    volumes:
      - db_data:/var/lib/mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress
    networks:
      - dockerwp
  # phpmyadmin
  phpmyadmin:
    depends_on:
      - db
    image: phpmyadmin
    restart: always
    ports:
      - "8080:80"
    environment:
      PMA_HOST: db
      MYSQL_ROOT_PASSWORD: password
    networks:
      - dockerwp
  # Wordpress
  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    volumes:
      - wordpress_data:/var/www/html
      - ./src:/var/www/html
    ports:
      - "8000:80"
    restart: always
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress
    networks:
      - dockerwp
networks:
  dockerwp:
volumes:
  db_data: {}
  wordpress_data: {}
```