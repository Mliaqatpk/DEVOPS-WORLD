---
title: "Day 28 : Jenkins Agents"
datePublished: Wed Jan 03 2024 07:12:49 GMT+0000 (Coordinated Universal Time)
cuid: clqxfyek300010akx1swr74jr
slug: day-28-jenkins-agents
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704265892962/3c32045e-4b06-4207-ba70-d5e90170d1ae.png
tags: aws, automation, jenkins, jenkins-devops, 90daysofdevops, day28

---

Here is the summary of the Day 28 of [**#90DaysOfDevOps**](https://github.com/LondheShubham153/90DaysOfDevOps) Challenge:

![](https://miro.medium.com/v2/resize:fit:853/1*0iAfr-MRabT2DfEpSqi3cg.png align="left")

## **Jenkins Master (Server)**

Jenkins’s server or master node holds all key configurations. Jenkins master server is like a control server that orchestrates all the workflow defined in the pipelines. For example, scheduling a job, monitoring the jobs, etc.

## **Jenkins Agent**

An agent is typically a machine or container that connects to a Jenkins master and this agent that actually execute all the steps mentioned in a Job. When you create a Jenkins job, you have to assign an agent to it. Every agent has a label as a unique identifier.

When you trigger a Jenkins job from the master, the actual execution happens on the agent node that is configured in the job.

A single, monolithic Jenkins installation can work great for a small team with a relatively small number of projects. As your needs grow, however, it often becomes necessary to scale up. Jenkins provides a way to do this called “master to agent connection.” Instead of serving the Jenkins UI and running build jobs all on a single system, you can provide Jenkins with agents to handle the execution of jobs while the master serves the Jenkins UI and acts as a control node.

## **Pre-requisites**

Let’s say we’re starting with a fresh Ubuntu 22.04 Linux installation. To get an agent working make sure you install Java ( same version as jenkins master server ) and Docker on it.

`Note:- While creating an agent, be sure to separate rights, permissions, and ownership for jenkins users.`

## **This blog covers:**

* Connecting master and agent using SSH.
    
* Setting up Jenkins agent
    
* Creating a freestyle Jenkins project and running it on particular agent.
    

## **Task -1**

* Create an agent by setting up a node on Jenkins
    
* Create a new AWS EC2 Instance and connect it to master(Where Jenkins is installed)
    
* The connection of master and agent requires SSH and the public-private key pair exchange.
    
* Verify its status under “Nodes” section.
    

Create two instances — Master and Agent.

In `Master` instance, install Java and Jenkins.

```plaintext
##Java

$ sudo apt update
$ sudo apt install openjdk-11-jre
$ java -version


##Jenkins

$ curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
$ echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
$ sudo apt-get update
$ sudo apt-get install jenkins
```

In `Agent` instance, install Java and Docker.

```plaintext
##Java

$ sudo apt update
$ sudo apt install openjdk-11-jre
$ java -version

##Docker

$ sudo apt-get update
$ sudo apt-get install docker.io
```

Verify all services are up and running in their respective instances. Go to Jenkins UI and set up Jenkins account by installing the required/recommended plugins.

Now, lets connect the master and agent.

The connection of master and agent requires SSH and the public-private key pair exchange.

In master,

```plaintext
$ ssh-keygen
$ cd .ssh
$ ls
```

ssh-keygen produces a public-private key pair.

```plaintext
id_rsa --> private key
id_rsa.pub --> public key
```

Copy the public key\[id\_[rsa.pub](http://rsa.pub)\] (to give to the agent node)

  
Now, in agent,

```plaintext
$ cd .ssh
$ vim authorized_keys
```

Edit authorized keys and paste the public key from the master instance.

Now, lets set up a new node. Go to **Manage Jenkins** and click on **Set up node**.

![](https://miro.medium.com/v2/resize:fit:875/1*4tH_3hPLs4afeWBCOolIRw.png align="left")

Enter Node name and select Permanent agent.

![](https://miro.medium.com/v2/resize:fit:875/1*k4QgGyyWROjpwk_VVXgRsg.png align="left")

Enter all details. Here, when we use labels for the agent, your master server would trigger the builds for the agent server.

![](https://miro.medium.com/v2/resize:fit:875/1*zySP8GBjVRuZW89rIUqIdA.png align="left")

For launch method, select ‘**Launch agents via SSH**’. Add public IP of Agent instance at the **Host** field.

![](https://miro.medium.com/v2/resize:fit:875/1*m0vGRTHns6eKGvD6hk4KqQ.png align="left")

For Credentials, add new credentials (if you do not already have them saved in Jenkins). Select ‘**SSH username with private key**’ . Fill all required details, and in the private key area add **Private key from master instance (id\_rsa).**

![](https://miro.medium.com/v2/resize:fit:875/1*GJKiT1aYemOyNf2805v3mA.png align="left")

Save the configuration details. And you can verify that the Agent is up and running if set-up properly.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704265158929/59d22f97-b816-4097-bd3b-6c417bc001d4.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704265368693/3700cd75-3dab-449b-a03e-11ce0cde979f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704265613133/c5787090-21ce-473b-b653-51820790ec29.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704265631608/8b8c4ecb-639a-48d2-8039-f9dacba8e02d.png align="center")