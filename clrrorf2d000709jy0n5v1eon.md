---
title: "Day 35 Mastering ConfigMaps and Secrets in Kubernetes🔒🔑🛡️"
datePublished: Wed Jan 24 2024 11:12:25 GMT+0000 (Coordinated Universal Time)
cuid: clrrorf2d000709jy0n5v1eon
slug: day-35-mastering-configmaps-and-secrets-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706094631982/9005f40a-b504-4dc8-b547-95dccfa13b02.png
tags: cloud, aws, kubernetes, cloud-computing, automation, 90daysofdevops, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, day35

---

Welcome to Day 35 of our Kubernetes exploration! Today, we're diving into the essential aspects of ConfigMaps and Secrets – powerful tools that allow you to manage configuration data and sensitive information within your Kubernetes applications.

### **1\. ConfigMaps: Managing Configuration Data**

ConfigMaps in Kubernetes are a resource object used to store configuration data in key-value pairs, separate from your application code. This separation enhances flexibility, allowing you to modify configurations without altering the application code.

#### Creating a ConfigMap:

Create a ConfigMap using a YAML file:

```plaintext
apiVersion: v1
kind: ConfigMap
metadata:
  name: my-app-config
data:
  database_url: "mysql://db-server:3306/mydatabase"
  api_key: "your_api_key_here"
```

Apply the ConfigMap to your cluster:

```plaintext
kubectl apply -f your-configmap-file.yaml
```

#### Using ConfigMaps in Pods:

Reference ConfigMap values in your Pod definition:

```plaintext
apiVersion: v1
kind: Pod
metadata:
  name: my-app-pod
spec:
  containers:
    - name: my-app-container
      image: your-container-image:latest
      env:
        - name: DATABASE_URL
          valueFrom:
            configMapKeyRef:
              name: my-app-config
              key: database_url
        - name: API_KEY
          valueFrom:
            configMapKeyRef:
              name: my-app-config
              key: api_key
```

### **2\. Secrets: Managing Sensitive Information**

Secrets in Kubernetes are similar to ConfigMaps but are specifically designed to store sensitive information, such as passwords or API keys. They are encoded in base64 by default.

#### Creating a Secret:

Create a Secret using a YAML file:

```plaintext
apiVersion: v1
kind: Secret
metadata:
  name: my-app-secret
type: Opaque
data:
  username: dXNlcm5hbWU=
  password: cGFzc3dvcmQ=
```

Apply the Secret to your cluster:

```plaintext
kubectl apply -f your-secret-file.yaml
```

#### Using Secrets in Pods:

Reference Secret values in your Pod definition:

```plaintext
apiVersion: v1
kind: Pod
metadata:
  name: my-app-pod
spec:
  containers:
    - name: my-app-container
      image: your-container-image:latest
      env:
        - name: DB_USERNAME
          valueFrom:
            secretKeyRef:
              name: my-app-secret
              key: username
        - name: DB_PASSWORD
          valueFrom:
            secretKeyRef:
              name: my-app-secret
              key: password
```

### **3\. Best Practices:**

* **Avoid Hardcoding Secrets:**
    
    * Leverage ConfigMaps and Secrets to externalize configurations and sensitive data, reducing the risk of exposure.
        
* **Regularly Rotate Secrets:**
    
    * Periodically rotate sensitive information stored in Secrets to enhance security.
        
* **Use Resource Policies:**
    
    * Implement RBAC (Role-Based Access Control) to control access to ConfigMaps and Secrets, limiting exposure.
        
    
    ### **What are ConfigMaps and Secrets in k8s**
    
    **A ConfigMap is an API object that stores configuration data for other objects**. It lets you decouple environment-specific configuration from container images, so moving your applications gets easier.
    
    **Kubernetes Secrets contain small amounts of sensitive data, such as passwords, tokens, or keys**. This type of information might be put in pod specs or a container image. However, thanks to a Secret, you can keep your confidential data separate from your app code.
    
    You can create a Secret independently of the pod that uses it. This ability reduces the risk of the data being exposed in the process of creating and editing your pods.
    
    ### Task 1:
    
    * Create a ConfigMap for your Deployment
        
    * Create a ConfigMap for your Deployment using a file or the command line
        
    
    ```plaintext
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: todo-app
    data:
      name: django-todo-app
      application: todo-app
      protocol: TCP
    ```
    
    Apply the changes using :
    
    ```plaintext
    kubectl apply -f configMap.yaml
    ```
    
    * Update the deployment.yml file to include the ConfigMap
        
    * ```plaintext
              apiVersion: apps/v1
              kind: Deployment
              metadata:
                name: config-todo-app
                labels:
                  app: todo
                namespace: todo-app
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
                      image: trainwithshubham/django-todo:latest
                      ports:
                      - containerPort: 8000
                      env:
                        - name: TODO_APP
                          valueFrom:
                            configMapKeyRef:
                              name: todo-app
                              key: application
        ```
        
        * Apply the updated deployment using the command:
            
        
    
    ```plaintext
        kubectl apply -f deployment.yml -n <namespace-name>
    ```
    
    * Verify that the ConfigMap has been created by checking the status of the ConfigMaps in your Namespace.
        
    
    The given command displays list of all ConfigMaps in your namespace
    
    ```plaintext
     kubectl get configmaps -n <namespace-name>
    ```
    
    The describe command is used to display the status imformation of all the ConfigMaps in your namespace.
    
    ```plaintext
     kubectl describe configmap <configmap-name> -n <namespace-name>
    ```
    
    This command displays the list of pods:
    
    ```plaintext
    kubectl get pod -n <namespace-name>
    ```
    
    Now, lets go inside one of the pods and see the key-value pair we declared earlier in the ConfigMap.
    
    ```plaintext
    kubectl -n <namespace-name> -it <pod-name> -- bash
    ```
    
    ### Task 2:
    
    * Create a Secret for your Deployment
        
    * Create a Secret for your Deployment using a file or the command line
        
        ```plaintext
          apiVersion: v1
          kind: Secret
          metadata:
            name: my-secret
          type: Opaque
          data:
            username: YWRtaW4=  # base64 encoded value for "admin"
            password: cGFzc3dvcmQyOTA2  # base64 encoded value for "password123"
        ```
        
        In this example, we’re creating a Secret called `my-secret` with two keys: `username` and `password`. The values for these keys are base64-encoded, so that the encoded sensitive information can be stored as plain text in a file.
        
        Lets apply the changes of `secret.yaml` :
        
    * ```plaintext
            kubectl apply -f secret.yaml -n <namespace-name>
        ```
        
        * Update the `deployment.yaml` file to include the Secret
            
        
    
    ```plaintext
        apiVersion: apps/v1
        kind: Deployment
        metadata:
          name: config-demo
          labels:
            app: todo
          namespace: todo-app
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
                image: trainwithshubham/django-todo:latest
                ports:
                - containerPort: 8000
                env:
                  - name: env_secret
                    valueFrom:
                      secretKeyRef:
                        name: my-secret
                        key: password
    ```
    
    * Apply the updated deployment using the command:
        
    
    ```plaintext
        kubectl apply -f deployment.yml -n <namespace-name>
    ```
    
    * Verify that the Secret has been created by checking the status of the Secrets in your Namespace.
        
    
    You can use the following command to verify that the Secret has been created :
    
    ```plaintext
    kubectl get secrets -n <namespace-name>
    ```
    
    To view the details of a specific Secret:
    
    ```plaintext
    kubectl describe secret <secret-name> -n <namespace-name>
    ```
    
    To see the key-value pairs of an environment variable in a ConfigMap inside a pod :
    
    ```plaintext
    kubectl get pod -n <namespace-name>
    kubectl exec -it <pod-name> -n <namespace-name> -- bash
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706094915659/f73a7132-e389-4ccf-96e4-32620a56f322.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706094919880/28ddf3ca-e486-4524-95ad-8a768c3bfda2.png align="center")
    

* That's it! You've just completed the task. 🎉
    
    Thank you so much for taking the time to read till the end! Hope you found this blog informative and helpful.
    
    Feel free to explore more of my content, and don't hesitate to reach out if need any assistance from me or in case of you have any questions.
    

### **Conclusion:**

Mastering ConfigMaps and Secrets in Kubernetes empowers you to efficiently manage configuration data and handle sensitive information securely. As you integrate these practices into your workflows, your Kubernetes applications become more scalable, maintainable, and, most importantly, secure. Stay tuned for more Kubernetes insights, and happy orchestrating! 🚀 #Kubernetes #ConfigMaps #Secrets #DevOps #ContainerOrchestration #LearningJourney