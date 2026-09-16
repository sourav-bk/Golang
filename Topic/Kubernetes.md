<details><summary><h3><mark> What Problem Solved K8s | Benefit </mark></h3></summary>

1. **Manual Deployment**

   If we had 100 containers, we had to start, stop, and manage them manually.
   
   **Using K8s :** Automates deployment and management of containers.

2. **Scaling Applications**

   When traffic increased, adding more application instances was difficult.
   
   **Using K8s :** Automatically scales applications up or down based on demand.

3. **High Availability**

   If a server or container crashed, the application could go down.
   
   **Using K8s :** Detects failed containers and automatically restarts or replaces them.

4. **Load Balancing**

   Distributing user requests across multiple application instances was complex.
   
   **Using K8s :** Built-in service discovery and load balancing.

5. **Resource Utilization**

   Servers were often underutilized or overloaded.
   
   **Using K8s :** Efficiently schedules containers across available nodes.

6. **Environment Consistency**

   Applications worked on a developer's machine but failed in production.
   
   **Using K8s :** Containers + orchestration provide consistent environments across Dev, Test, and Production.

7. **Rolling Updates and Rollbacks**

   Updating applications could cause downtime.
   
   **Using K8s :** Supports zero-downtime rolling updates and easy rollbacks.  
</details>   

<details><summary><h3><mark> K8S Architecture </mark></h3></summary>

Kubernetes follows a Master-Worker (Client-Server) architecture. The cluster consists of a Control Plane (Master) that manages the cluster, and Worker Nodes that run the actual application workloads.

   **Control Plane :**
   
   The Control Plane is the brain of Kubernetes. It makes global decisions about the cluster (scheduling, detecting & responding to events). In production, it runs across multiple machines for high availability.
   
   **Responsibilities:** Cluster management, Scheduling workloads, Maintaining desired state, Monitoring cluster health.

   <details><summary>Components of Control Plane</summary>
      
   - **API Server (kube-apiserver)**
     The API Server is the entry point of Kubernetes.Everything communicates through API Server.
     It's Accepts REST API requests. Authentication & Authorization and Validates the requests. then Stores cluster state in ETCD or Communication with ETCD.
     
   - **ETCD**
     ETCD is a distributed key-value database. Purpose to Stores cluster configuration.., Stores pod information.., Stores node information.., Stores secrets/configmaps.
     
   - **Scheduler (kube-scheduler)**
   - **Controller Manager (kube-controller-manager)**
   - **Cloud Controller Manager**
     
   </details>

   **Worker Node :**

   

   <details><summary>Components of Worker Node</summary>
   
   - **Kubelet**
   - **Kube Proxy**
   - **Container Runtime**
   - **Pods**
   - **Deployment**
   - **ReplicaSet**
   - **Service**
   - **Ingress**
   - **ConfigMap**
   - **Secret**
   
   </details>

   
</details>
