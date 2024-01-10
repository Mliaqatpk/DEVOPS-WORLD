---
title: "🚀 Day 34: Working with Services in Kubernetes🚀"
datePublished: Wed Jan 10 2024 11:20:53 GMT+0000 (Coordinated Universal Time)
cuid: clr7owda6000009l2g6s9c5gi
slug: day-34-working-with-services-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704885578652/82a8ab47-c8cd-4a43-a235-6356d799eb5b.png
tags: kubernetes, cloud-computing, automation, 90daysofdevops, 90daysofdevops-chanllenge, tws, kubeweek, kubeweekchallenge, day34

---

Day 34 of *#90daysofdevops*

Hey Techies! Welcome to this blog

In this blog, we are going to start working with Services in Kubernetes

### What are Services in K8s

In Kubernetes, Services are objects that provide stable network identities to Pods and abstract away the details of Pod IP addresses. Services allow Pods to receive traffic from other Pods, Services, and external clients.

This is like a phone directory for Pods. Since Pods can came and go , a service provides a stable "address" so that other parts of your application can find them.

Welcome back to our Kubernetes journey! On Day 34, we're diving into the essential task of working with Services in Kubernetes. Services play a crucial role in enabling communication between different parts of your application, abstracting away the complexities of networking. Let's explore the key tasks associated with Services in Kubernetes.

### **Task-1:**

### **Creating a Service for todo-app Deployment**

Step 1: Service Definition

Create a Service definition for your todo-app Deployment. Open a new file, `service.yml`, and add the following configuration:

### **1\. Creating a Service:**

To create a service, you'll need a YAML file that defines its specifications. Here's a simple example of a ClusterIP service:

```plaintext
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
spec:
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
```

This service selects Pods with the label `app: my-app` and exposes them internally on port 80.

Step 2: Applying the Service Definition

Apply the Service definition to your Kubernetes cluster using the following command:

Apply the service to your cluster using the following command:

```plaintext
kubectl apply -f your-service-file.yaml
```

### **2\. Viewing Services:**

Step 3: Verifying the Service

Verify that the Service is working by accessing the todo-app using the Service's IP and Port within your Namespace.

```plaintext
kubectl get svc -n <namespace-n
```

To see a list of services in your cluster, use the following command:

```plaintext
kubectl get services
```

This will display information about each service, including its name, type, cluster IP, external IP (if applicable), and ports.

### **3\. Accessing Services:**

### **Task-2:**

### Creating a ClusterIP Service for Internal Access

Understanding ClusterIP Service

The ClusterIP service type exposes the Service on a cluster-internal IP. This type of Service is accessible only within the cluster, making it ideal for internal communication between Pods.

Step 1: ClusterIP Service Definition

Create a ClusterIP Service definition for your todo-app Deployment. Open a new file, `cluster-ip-service.yml`, and add the following configuration:

* **ClusterIP Service:**
    
    * If your service is of type `ClusterIP`, it's accessible only within the cluster. Other applications within the same cluster can communicate with it using the Cluster IP.
        
* **NodePort Service:**
    
    * If your service is of type `NodePort`, it opens a port on all nodes, allowing external access. Use the NodePort to access your service externally.
        
    * ```plaintext
          apiVersion: v1
          kind: Service
          metadata:
            name: todo-app-cluster-ip-service
          spec:
            selector:
              app: todo-app
            ports:
              - protocol: TCP
                port: 80
                targetPort: 8000
            type: ClusterIP
        ```
        

```plaintext
kubectl get nodes -o wide  # Get external IP of nodes
```

Now, you can access your service using the Node IP and NodePort.

Step 2: Applying the ClusterIP Service Definition

```plaintext
kubectl apply -f cluster-ip-service.yml -n <namespace-name>
```

Apply the ClusterIP Service definition to your Kubernetes cluster using the following command:

Step 3: Verifying the ClusterIP Service

Verify that the ClusterIP Service is working by accessing the todo-app from another Pod in the cluster within your Namespace.

```plaintext
kubectl get svc -n <namespace-name>
```

Access your todo-app from another Pod using the ClusterIP.

### **4\. Updating Services:**

If you need to update your service, modify the corresponding YAML file and apply the changes:

```plaintext
kubectl apply -f your-updated-service-file.yaml
```

### **5\. Deleting Services:**

To delete a service, use the `kubectl delete service` command followed by the service name:

```plaintext
kubectl delete service my-app-service
```

### **6\. Service Discovery:**

Services in Kubernetes come with built-in DNS support. You can reach a service using its name and namespace. For example, if you have a service named `my-app-service` in the default namespace, other services can reach it at `my-app-service.default.svc.cluster.local`.

### **Task-3:**

### Creating a LoadBalancer Service for External Access

Step 1: LoadBalancer Service Definition

Create a LoadBalancer Service definition for your todo-app Deployment. Open a new file, `load-balancer-service.yml`, and add the following configuration:

```plaintext
apiVersion: v1
kind: Service
metadata:
  name: todo-app-load-balancer-service
spec:
  selector:
    app: todo-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8000
  type: LoadBalancer
```

Step 2: Applying the LoadBalancer Service Definition

Apply the LoadBalancer Service definition to your Kubernetes cluster using the following command:

```plaintext
kubectl apply -f load-balancer-service.yml -n <namespace-name>
```

**Step 3: Verifying the LoadBalancer Service**

Verify that the LoadBalancer Service is working by accessing the todo-app from outside the cluster within your Namespace.

```plaintext
kubectl get svc -n <namespace-name>
```

Access your todo-app from outside the cluster using the provided external IP.

That's it! You've just completed the task. 🎉

### **Conclusion:**

Mastering the art of working with Services in Kubernetes is pivotal for seamless communication within your application. As you experiment and deploy services in your cluster, keep exploring the diverse service types and their use cases. Stay tuned for more Kubernetes adventures, and happy coding! 🚀 #Kubernetes #Services #DevOps #ContainerOrchestration #LearningJourney