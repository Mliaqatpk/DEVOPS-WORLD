---
title: "ᴅᴀʏ 36 ᴍᴀɴᴀɢɪɴɢ ᴘᴇʀꜱɪꜱᴛᴇɴᴛ ᴠᴏʟᴜᴍᴇꜱ ɪɴ ʏᴏᴜʀ ᴅᴇᴘʟᴏʏᴍᴇɴᴛ"
datePublished: Thu Jan 25 2024 10:24:01 GMT+0000 (Coordinated Universal Time)
cuid: clrt2h0il000209jo5j92ciq7
slug: 36
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706178174254/1d984c9a-b37a-461b-9806-f0d6ecca71b8.png
tags: cloud, aws, kubernetes, cloud-computing, automation, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, 90daysofdevopschallenge, tws, kubeweek

---

Hey Techies! Welcome to this blog

In this blog, we are going to start with Managing Persistent Volumes in Your Deployment

### **What are Persistent Volumes (PVs)?**

A PersistentVolume (PV) is a storage resource in the cluster that has been provisioned by an administrator or dynamically provisioned using Storage Classes.

PV is the way to define the storage data, such as storage classes or storage implementations. Unlike ordinary volumes, PV is a resource object in a Kubernetes cluster; creating a PV is equivalent to creating a storage resource object. To use this resource, it must be requested through persistent volume claims (PVC). A PVC volume is a request for storage, which is used to mount a PV into a Pod. The cluster administrator can map different classes to different service levels and different backend policies.

Persistent storage volume can be carried out through the YAML configuration file and specify which plugin type to use. The following is a YAML configuration file for persistent storage volume. This configuration file requires 5Gi of storage space to be provided. The storage mode is `Filesystem`, the access mode is `ReadWriteOnce`, and the persistent storage volume is recycled through the `Recycle` recycling policy. Finally, the storage class is specified as `slow`, and the NFS plug-in type is `used`.

#### **Access Modes**

* `ReadOnlyMany(ROX)` allows being mounted by multiple nodes in read-only mode.
    
* `ReadWriteOnce(RWO)` allows being mounted by a single node in read-write mode.
    
* `ReadWriteMany(RWX)` allows multiple nodes to be mounted in read-write mode.
    

1. **Define Persistent Volume (PV):**
    
    * Create a Persistent Volume that represents a piece of storage in your cluster.
        
    * Specify the capacity, access modes, and storage class if applicable.
        
2. **Define Persistent Volume Claim (PVC):**
    
    * Create a Persistent Volume Claim that requests a specific amount of storage with defined access modes.
        
    * The PVC binds to an available PV that meets its criteria.
        
3. **Attach Persistent Volume to Deployment:**
    
    * Modify your deployment configuration to use the PVC as a volume.
        
    * Ensure your application is configured to read and write data to the mounted volume.
        
4. **Deployment Update:**
    
    * Update your deployment to apply the changes. This might involve scaling down the current deployment, applying the changes, and then scaling it back up.
        
5. **Monitoring:**
    
    * Regularly monitor the status of your persistent volumes and claims.
        
    * Check for any errors or warnings related to storage.
        
6. **Backup and Recovery:**
    
    * Implement a backup strategy for your persistent data.
        
    * Have a plan for recovering data in case of failures.
        
7. **Scaling:**
    
    * Consider how your persistent storage scales with the overall deployment.
        
    * If your storage needs increase, ensure you have a strategy for adding more capacity.
        
8. **Security and Access Control:**
    
    * Implement proper security measures to protect your persistent data.
        
    * Control access to the storage based on the principle of least privilege.
        
9. **Documentation:**
    
    * Keep detailed documentation about your persistent volumes, claims, and deployment configurations.
        
    * Document any changes made to the persistent storage setup.
        
10. **Testing:**
    
    * Regularly test the resilience and performance of your persistent storage.
        
    * Simulate failure scenarios to ensure your data can be recovered.
        

```plaintext
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv0005
spec:
  capacity:
   storage: 5Gi
  volumeMode: Filesystem
  accessModes:
   - ReadWriteOnce
  persistentVolumeReclaimPolicy: Recycle
  storageClassName: slow
  mountOptions:
   - hard
   - nfsvers=4.1
  nfs:
   path: /tmp
   server: 172.17.0.2
```

### **What are Persistent Volume Claims (PVCs)?**

PVC is a declaration defining the request for storage data usage, which is mounted into a Pod for use. PVC is configured for use by developers, who do not necessarily care about the specific implementation of the underlying data storage, but more so about the business-related data storage size, access methods, etc.

Here is the configuration file for the `PersistentVolumeClaim`:

```plaintext
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pv0004
spec:
  storageClassName: manual
  accessModes:
   - ReadWriteOnce
  resources:
   requests:
    storage: 3Gi
```

## **Lifecycle of PV and PVC**

In a Kubernetes cluster, a PV exists as a storage resource in the cluster. PVCs are requests for those resources and also act as claim checks to the resource. The interaction between PVs and PVCs follows this lifecycle:

* `Provisioning` - the creation of the PV, either directly (static) or dynamically using `StorageClass`.
    
* `Binding` - assigning the PV to the PVC.
    
* `Using` - Pods use the volume through the PVC.
    
* `Reclaiming` - the PV is reclaimed, either by keeping it for the next use or by deleting it directly from the cloud storage.
    

A volume will be in one of the following states:

* `Available` - this state shows that the PV is ready to be used by the PVC.
    
* `Bound` - this state shows that the PV has been assigned to a PVC.
    
* `Released` - the claim has been deleted, but the cluster has not yet reclaimed the resource.
    
* `Failed` - this state shows that an error has occurred in the PV.
    

### Task 1:

**Add a Persistent Volume to your Deployment todo app.**

**Create a Persistent Volume using a file on your node.**

This is a piece of storage in your cluster that can be dynamically provisioned and claimed by a Pod. To create a Persistent Volume, you can use a file on your node. You can create a YAML file, called **pv.yml**, that defines the Persistent Volume. This file should include the size of the storage, the access modes, and the path to the file on your node.

* Create a file `pv.yaml` and write the code for Persistent Volume.
    

```plaintext
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-django-todo-app
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  hostPath:
    path: "/mnt/data"
```

```plaintext
kubectl apply -f pv.yaml
```

* Create a file `pvc.yaml` and write the code for Persistent Volume Claim.
    

```plaintext
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-django-todo-app
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 500Mi
```

* Create a file `deploymentvolumes.yaml` and write the code for Deployment.
    

```plaintext
Create a file deploymentvolumes.yaml and write the code for Deployment.
```

## **Task 2:**

* Connect to a Pod in your Deployment using the command :
    
    ```plaintext
      kubectl exec -it <pod-name> -- /bin/bash
    ```
    
    * Here we can create a file in the pod and check the data in the Persistent Volume in the interactive shell.
        
    
    ```plaintext
    cd /tmp/app
    ```
    
    * At last exit from the pod.
        
    * Verify that you can access the data stored in the Persistent Volume from within the Pod by checking the contents of the file you created in the Pod.
        
    
    That's it! You've just completed the task. 🎉
    
    Thank you so much for taking the time to read till the end! Hope you found this blog informative and helpful.
    
    Feel free to explore more of my content, and don't hesitate to reach out if need any assistance from me or in case of you have any questions.
    
    Happy Learning!