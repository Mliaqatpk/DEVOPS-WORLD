---
title: "Day 32 Launching your Kubernetes Cluster with Deployment"
datePublished: Tue Jan 09 2024 08:32:00 GMT+0000 (Coordinated Universal Time)
cuid: clr63fccb000s08l382olbo66
slug: day-32-launching-your-kubernetes-cluster-with-deployment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704788785841/4013a230-cec6-4370-a7cc-d84152411477.png
tags: aws, kubernetes, cloud-computing, automation, 90daysofdevops, shubhamlondhe, trainwithshubham, kubeweekchallenge, batch-5

---

**Introduction:**

Welcome back to our Kubernetes journey! In the last few days, we've covered the basics of Kubernetes, from understanding its architecture to setting up your environment. Today, on Day 32, we're diving into the exciting world of launching your Kubernetes cluster using deployments. Deployments are a key concept in Kubernetes, allowing you to manage and scale your applications effortlessly.

**Understanding Deployments:**

In Kubernetes, a deployment is an abstraction that defines the desired state for your application. It enables you to declaratively manage your application, handling updates and rollbacks with ease. Deployments are crucial for maintaining the desired number of replicas, managing updates to applications, and rolling back to previous versions if needed.

**Setting Up Your Kubernetes Cluster:**

Before we proceed with deployments, make sure you have a running Kubernetes cluster. If you haven't set one up yet, you can follow the instructions from our previous blog posts. Once your cluster is up and running, we're ready to get started.

**Creating a Deployment:**

1. **Define Your Deployment:** Create a YAML file that describes your deployment. This file includes specifications for the container image, replicas, and any other necessary configurations. Here's a simple example:
    

```plaintext
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app-container
        image: your-container-image:latest
```

**Apply the Deployment:** Use the `kubectl apply` command to create or update the deployment based on the YAML file you created:

```plaintext
kubectl apply -f your-deployment-file.yaml
```

Scaling Your Application:

One of the powerful features of Kubernetes is the ability to scale your application effortlessly. If, for example, you want to increase the number of replicas from 3 to 5, you can use the following command:

```plaintext
kubectl scale deployment my-app-deployment --replicas=5
```

Updating Your Application:

When it's time to update your application, you can simply modify the container image in your deployment YAML file and reapply it:

```plaintext
kubectl apply -f your-updated-deployment-file.yaml
```

Rolling Back to a Previous Version:

In case something goes wrong with the update, Kubernetes makes it easy to roll back to a previous version:

```plaintext
kubectl rollout undo deployment my-app-deployment
```

## What is Deployment in k8s

A Deployment provides a configuration for updates for Pods and ReplicaSets.

You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate. You can define Deployments to create new replicas for scaling, or to remove existing Deployments and adopt all their resources with new Deployments.

## Today's task let's keep it very simple.

## Task-1:

**Create one Deployment file to deploy a sample todo-app on K8s using "Auto-healing" and "Auto-Scaling" feature**

* add a deployment.yml file (sample is kept in the folder for your reference)
    
* apply the deployment to your k8s (minikube) cluster by command `kubectl apply -f deployment.yml`
    

Let's make your resume shine with one more project ;)

**Here are the key aspects of a Kubernetes Deployment:**

1. Desired State
    
2. Rolling Updates and Rollbacks
    
3. Scaling
    
4. High Availability
    
5. Self-healing
    

Let's start by creating a deployment.yml file. This YAML file contains the configuration details of our deployment. Here's a sneak peek:

```plaintext
apiVersion: apps/v1
kind: Deployment
metadata:
  name: todo-app
  labels:
    app: todo
spec:
  replicas: 2
  selector:
    matchLabels:
      app: todo
  template:
    metadata:
      labels:
        app: todo
    spec:
      containers:
      - name: todo
        image: trainwithshubham/django-todo
        ports:
        - containerPort: 8000
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704788591958/290fdb91-3fe4-4e18-9d23-728eb7c20604.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704789019801/b9d139da-0046-4ce1-b10d-90264d973246.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704788627138/2162001c-d090-4af8-8cee-08447692fdf9.png align="center")

```plaintext
apiVersion: apps/v1
kind: Deployment
metadata:
  name:  todo-app
  labels:
    name:  todo
spec:
  replicas: 2
  selector:
    matchLabels:
    app: todo
  template:
    metadata:
      labels:
        app : todo
    spec:
      containers:
      -name: todo
       image: trainwithshubham/django-todo
       ports:
       - containerPort: 8000
         port:  Port
         protocol: TCP
```

Conclusion:

Congratulations on launching your Kubernetes cluster with deployment! With this fundamental concept, you're now equipped to manage, scale, and update your applications seamlessly. As you continue your Kubernetes journey, keep exploring other features and best practices to enhance your container orchestration skills. Stay tuned for more exciting topics on our Kubernetes adventure!