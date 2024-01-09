---
title: "Day 33: Navigating Kubernetes - Namespaces and Services Unveiled"
datePublished: Tue Jan 09 2024 10:12:16 GMT+0000 (Coordinated Universal Time)
cuid: clr6709vd000b09l52iiaapnv
slug: day-33-navigating-kubernetes-namespaces-and-services-unveiled
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704794976684/ea00b044-cd8b-49ec-b5de-14a41569cae2.png
tags: kubernetes, automation, 90daysofdevops, shubhamlondhe, trainwithshubham

---

Greetings, Kubernetes enthusiasts! Today, on Day 33 of our Kubernetes exploration, we're delving into two fundamental concepts that play a crucial role in orchestrating containerized applications: Namespaces and Services. 🚢💡

Day 33 of *#90daysofdevops*

Hey Techies! Welcome to this blog

In this blog, we are going to start working with Namespaces and Services in Kubernetes

### What are Namespaces and Services in k8s

### **What are Namespaces?**

A namespace is a group of related elements that each have a unique name and identifier. A namespace is used to uniquely identify one or more names from other similar names of different objects, groups, or the namespace in general.

A mechanism to attach authorization and policy to a subsection of the cluster

**Understanding Namespaces:**

In the vast Kubernetes landscape, Namespaces act as virtual clusters within a physical cluster, providing a way to divide and conquer resources. Think of them as a powerful organizational tool, allowing you to partition your cluster, isolate resources, and manage access control effectively.

🔍 **Key Benefits of Namespaces:**

* **Isolation:** Keep your applications and resources neatly separated.
    
* **Resource Management:** Allocate resources based on project, team, or environment.
    
* **Access Control:** Define fine-grained access policies for different namespaces.
    
* ![Azure AKS Kubernetes Namespaces Introduction - Azure Kubernetes Service](https://stacksimplify.com/course-images/azure-kubernetes-service-namespaces-3.png align="left")
    

**Creating a Namespace:**

Creating a namespace is a breeze. Use the following command to carve out your dedicated space:

```plaintext
kubectl create namespace your-namespace-name
```

**Working with Services:**

Now, let's shift our focus to Services - a critical component for enabling communication between different parts of your application, both internally and externally.

🌐 **Key Functions of Services:**

* **Service Discovery:** Simplify communication by abstracting the underlying infrastructure.
    
* **Load Balancing:** Automatically distribute traffic among pods.
    
* **Stable Network Endpoint:** Ensure a stable endpoint for your application.
    

**Creating a Service:**

Define a service to expose your application within the cluster or make it accessible externally. Here's a simple example:

```plaintext
apiVersion: v1
kind: Service
metadata:
  name: your-service-name
spec:
  selector:
    app: your-app-label
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
  type: ClusterIP
```

Apply the service configuration using:

```plaintext
kubectl apply -f your-service-config.yaml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703323569535/287577d5-daf3-40ab-86f7-59d863b595b6.webp?auto=compress,format&format=webp align="left")

**Connecting the Dots:**

Now, tie it all together! Deploy your application pods in a specific namespace, and connect them using services. This creates a structured, scalable, and maintainable architecture for your containerized applications.

### **Task 1:**

* Create a Namespace for your Deployment
    
* Use the command `kubectl create namespace <namespace-name>` to create a Namespace
    
* Update the deployment.yml file to include the Namespace
    
* Apply the updated deployment using the command: `kubectl apply -f deployment.yml -n <namespace-name>`
    
* Verify that the Namespace has been created by checking the status of the Namespaces in your cluster.
    

step:01 check the in-build namespace in the cluster

you can write kubectl = k and namespace = ns

```plaintext
kubectl get ns # to check the namespace
kubectl create namespace <namespace-name> # to create the namespace
kubctl create namespace todo
kubectl get ns #to gets the namespace
```

Update the deployment.yml file to include the Namespace

```plaintext
apiVersion: apps/v1
kind: Deployment
metadata:
  name: todo-app
  namespace: todo
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

Apply the updated deployment using the command: `kubectl apply -f deployment.yml -n <namespace-name>`

```plaintext
kubeclt apply -f deployment.yml -n todo
```

* Verify that the Namespace has been created by checking the status of the Namespaces in your cluster.
    
* ```plaintext
      kubectl get namespaces
    ```
    

### **Task 2:**

* Read about Services, Load Balancing, and Networking in Kubernetes. Refer official documentation of kubernetes.
    
    **Services in Kubernetes:**
    
    **Services** in Kubernetes provide a way to abstract and expose a set of Pods as a network service. They act as an intermediary between clients and Pods, ensuring that clients can reliably connect to the appropriate Pods, even if the Pods are scaled up, down, or replaced. Services come in several types:
    
    1. **ClusterIP**: This is the default type. It exposes the Service on an internal cluster IP, making it accessible only within the cluster. It's commonly used for internal communication between components.
        
    2. **NodePort**: It exposes the Service on a static port on each node's IP address. This allows external access to the Service. While it's accessible from outside the cluster, it typically requires some form of external load balancing for production use.
        
    3. **LoadBalancer**: This type requests a cloud provider's load balancer to expose the Service externally. It's suitable for applications that need external access, and it works with cloud providers that support load balancers.
        
    4. **ExternalName**: This type maps the Service to an external DNS name, redirecting requests to that DNS name. It's used for accessing services outside the cluster.
        

**Load Balancing in Kubernetes:**

Kubernetes uses load balancing to distribute incoming network traffic across multiple Pods or endpoints that belong to a Service. This provides high availability, scalability, and fault tolerance for applications. Here's how it works:

* When you create a Service of type `ClusterIP` or `NodePort`, Kubernetes sets up a virtual IP address for the Service. For `NodePort`, it also opens a specific port on each node.
    
* When clients send requests to the Service's IP address and port, the Kubernetes Service acts as a load balancer. It selects one of the Pods that match the Service's selector and forwards the request to that Pod.
    
* The load balancer evenly distributes traffic across all available Pods, ensuring that no single Pod is overwhelmed with requests.
    
* If a Pod becomes unhealthy or is scaled down, the load balancer automatically adjusts and routes traffic only to healthy Pods.
    
* This load-balancing mechanism simplifies scaling applications up or down without affecting external or internal client access.
    
    **Networking in Kubernetes:**
    

Kubernetes provides a flexible and robust networking model to facilitate communication between Pods and Services. Key networking concepts include:

1. **Pod-to-Pod Communication**: Pods can communicate with each other directly using their IP addresses. Kubernetes assigns each Pod an IP within the cluster's network, allowing seamless communication.
    
2. **Service Discovery**: Kubernetes DNS (Domain Name System) allows Pods and Services to discover each other by name. Pods can access Services using the Service name as a DNS entry.
    
3. **Network Policies**: Network policies allow you to define rules for network communication between Pods, providing fine-grained control over traffic flow and access within the cluster.
    
4. **Ingress Controllers**: Ingress controllers manage external access to Services, typically by providing HTTP and HTTPS routing and load balancing. They allow you to define routing rules to access Services from outside the cluster.
    
5. **CNI (Container Network Interface)**: Kubernetes supports multiple CNI plugins that enable network providers to integrate their network solutions with Kubernetes. CNI plugins handle network configuration and management for Pods.
    

Overall, Kubernetes provides a powerful networking model that allows you to build scalable, resilient, and well-connected applications within the cluster and exposes them to external users when needed.

That's it! You've just completed the task. 🎉

Thank you so much for taking the time to read till the end! Hope you found this blog informative and helpful.

Feel free to explore more of my content, and don't hesitate to reach out if need any assistance from me or in case of you have any questions.

Happy Learning!

👨‍💻 **Stay Tuned:**

* Discover advanced strategies for namespace management.
    
* Explore different service types and their use cases.
    
* Tips and best practices for a well-orchestrated Kubernetes environment.
    

Embark on this journey with me as we master Kubernetes one concept at a time! Check out the full details in today's blog post: Day 33: Working with Namespaces and Services in Kubernetes

#Kubernetes #Namespaces #Services #ContainerOrchestration #TechJourney #LearnK8s #Day33