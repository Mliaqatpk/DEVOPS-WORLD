---
title: "Day 31 Launching your First Kubernetes Cluster with Nginx running"
datePublished: Thu Jan 04 2024 11:26:30 GMT+0000 (Coordinated Universal Time)
cuid: clqz4gh4o00070aky2ej38ofs
slug: day-31-launching-your-first-kubernetes-cluster-with-nginx-running
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704367514565/a582980d-e706-4a21-a939-378db6cc7299.png
tags: aws, kubernetes, automation, orchestration, 90daysofdevops, shubhamlondhe, trainwithshubham, 90daysofdevops-chanllenge, tws, kubeweekchallenge

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704367203164/9bdc7794-3c3e-41cb-93a3-c976c958f802.png align="center")

**Task-01:**

Install Minikube on Your Local

A Simple Installation Guide

# minikube start

**Step 1**

To install the latest minikube **stable** release on **x86-64** **Linux** using **binary download**:

curl -LO [https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64](file:///C:/Users/MALIKL~1/AppData/Local/Temp/msohtmlclip1/01/clip_filelist.xml)

sudo install minikube-linux-amd64 /usr/local/bin/minikube

**Step 2**

## **Start your cluster**

From a terminal with administrator access (but not logged in as root), run:

minikube start

## **Interact with your cluster**

If you already have kubectl installed (see [documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl/)), you can now use it to access your shiny new cluster:

kubectl get po -A

Alternatively, minikube can download the appropriate version of kubectl and you should be able to use it like this:

minikube kubectl -- get po -A

You can also make your life easier by adding the following to your shell config

alias kubectl="minikube kubectl --"

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704366943192/441a19c9-df21-420a-bb0b-c57bfc611e4a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704366994265/6f42f4fe-be93-4dbc-82b1-a10c9e16b50d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704367012445/0a81488d-3136-4175-861b-36c0fee74b02.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704367035412/ae5fd6ed-7fe7-47ba-aca4-0dc76583c189.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704367043262/3386b8fa-5ab6-4a10-8b52-1fe76adc3fff.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704367071650/182e118a-7978-4124-bd49-09be4db41886.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704367085955/7134ae7f-4097-4e71-b284-d095fdec384f.png align="center")

**What is minikube?**

Minikube is an open-source tool that facilitates running Kubernetes clusters locally on a single machine. Kubernetes is a powerful container orchestration platform used for automating the deployment, scaling, and management of containerized applications. Minikube allows developers to set up a lightweight, single-node Kubernetes cluster on their local development machines for testing and experimentation.

**Key features of Minikube include:**

Local Kubernetes Cluster: Minikube provides a simplified way to run a local Kubernetes cluster on your laptop or workstation.

Isolation: It isolates the Kubernetes environment from the rest of the system, ensuring that the local cluster doesn't interfere with other installed software.

Easy Setup: Minikube aims to make it easy to set up and use Kubernetes locally. It can be particularly useful for developers who want to test their applications in a Kubernetes environment without the need for a full-scale, production-like cluster.

Support for Hypervisors and Containers: Minikube supports various hypervisors, such as VirtualBox, Hyper-V, and KVM, allowing users to choose the virtualization technology that best fits their environment. It also supports container runtimes like Docker and containerd.

Integration with kubectl: Minikube seamlessly integrates with kubectl, the command-line tool for interacting with Kubernetes clusters. This allows developers to use familiar commands to manage the local cluster.

Addon Support: Minikube supports various add-ons that extend the functionality of the local Kubernetes cluster, such as the Kubernetes Dashboard, Heapster, and more.

Using Minikube, developers can develop, test, and debug their applications in a Kubernetes environment without the need for a dedicated cloud or on-premises Kubernetes cluster. It's a valuable tool for those who want to get hands-on experience with Kubernetes or for teams looking to streamline their development workflows.

**Features of minikube**

Ans :- Features of minikube:

(a) Supports the latest Kubernetes release (+6 previous minor versions)

(b) Cross-platform (Linux, macOS, Windows)

(c) Deploy as a VM, a container, or on bare-metal

(d) Multiple container runtimes (CRI-O, containerd, docker)

(e) Direct API endpoint for blazing fast image load and build

(f) Advanced features such as LoadBalancer, filesystem mounts, FeatureGates, and network policy

(g) Addons for easily installed Kubernetes applications

(h) Supports common CI environments

Task-02:

Create your first pod on Kubernetes through minikube.

**Let's create a folder for the pod.**

**mkdir Minikube\_Project**

**Let's Deploy Nginx!**

**Let's create a namespace for the Nginx pod.**

**kubectl create namespace nginx**

**kubectl get namespaces**

**Now, Create YAML Configuration: Define a simple YAML file describing your Nginx pod. Create a pod.yml**

```plaintext
vi pod.yml
```

```plaintext
   apiVersion: v1
 kind: Pod
 metadata:
   name: nginx-pod
 spec:
   containers:
   - name: nginx-container
     image: nginx:latest
     ports:
     - containerPort: 80
```

**Apply Configuration:** 

**Use the kubectl apply command to create the pod.**

   **kubectl apply -f pod.yml**

**Check Pod Status:**

 **Confirm the pod's creation and its running status.**

 **kubectl get pods**

  **That's it! You've just completed the task. 🎉 Thank you so much for taking the time to read till the end! Hope you found this blog informative and helpful.**