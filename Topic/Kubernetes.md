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

   #### Control Plane
   
   The Control Plane is the brain of Kubernetes. It makes global decisions about the cluster (scheduling, detecting & responding to events). In production, it runs across multiple machines for high availability.
   
   **Responsibilities:** Cluster management, Scheduling workloads, Maintaining desired state, Monitoring cluster health.

   <details><summary>Components of Control Plane</summary>
      
   - **API Server (kube-apiserver)**

     The API Server is the entry point of Kubernetes.Everything communicates through API Server.
     It's Accepts REST API requests. Authentication & Authorization and Validates the requests. then Stores cluster state in ETCD or Communication with ETCD.
     
   - **ETCD**
     
     ETCD is a distributed key-value database. Purpose to Stores cluster configuration.., Stores pod information.., Stores node information.., Stores secrets/configmaps.
     
   - **Scheduler (kube-scheduler)**

     The Kubernetes Scheduler (kube-scheduler) is a core control plane component responsible for assigning newly created or unscheduled Pods to the most optimal Nodes in a cluster.
     
   - **Controller Manager (kube-controller-manager)**
     
     The Controller Manager (kube-controller-manager) is a critical component of the Kubernetes control plane. Its primary role is to run various background control loops that ensure the actual state of our cluster matches the desired state defined in our configuration and give the Auto-healing and Scaling capability Functionality.
   
   - **Cloud Controller Manager**
     
     The Cloud Controller Manager (CCM) is a specialized component of the Kubernetes control plane that acts as a bridge between your Kubernetes cluster and the underlying cloud infrastructure
   </details>

   #### Worker Node

   Worker Node in Kubernetes acts as the data plane or the machine that executes applications. It is responsible for running containerized workloads, managing networking, and reporting back to the control plane. 

   <details><summary>Components of Worker Node</summary>
   
   - **Kubelet**

     The Kubelet is a fundamental component of the Kubernetes worker node . It acts as the primary agent responsible for the lifecycle of applications running on that node .

     Key responsibilities include:
     
     - **Pod Management:**
       
       It is responsible for running and maintaining the Pods assigned to the node, ensuring they are always in a running state .
       
     - **Health Monitoring & Auto-healing:**
       
       It continuously checks if the Pods are healthy; if a Pod is not running correctly, it informs the Control Plane so that corrective actions can be taken, supporting Kubernetes' auto-healing capabilities .
       
     - **Runtime Coordination:**

       It communicates with the container runtime (such as containerd or CRI-O) to actually execute the containers defined within the Pod specifications .

   - **Kube Proxy**

     In Kubernetes, kube-proxy is a critical network component that runs on every worker node (45:09). It acts as the network manager for your cluster, ensuring that traffic reaches the correct Pod.
     
     Key responsibilities :
     - **Networking & Service Discovery:**

       It assigns IP addresses to Pods and ensures that services are discoverable within the cluster.

     - **Load Balancing:**

       It implements load-balancing logic. If you have multiple replicas of a Pod, it distributes incoming traffic across them.
       
     - **IP Table Management:**

       It continuously monitors the API Server for changes to service configurations and updates the node's IP tables or IPVS rules to enforce network traffic routing.

     
   - **Container-Runtime**
     
     Container-Runtime is the essential software component responsible for actually pulling container images and running the containers themselves on a worker node. It manages the low-level lifecycle of containers—starting, stopping, and handling their execution—based on specific instructions received from the Kubelet.
     
   - **Pods**
     
     A Pod is the smallest and most basic deployable unit in Kubernetes. Unlike in Docker, where you deploy individual containers, in Kubernetes, you deploy Pods that act as a wrapper around one or more containers.

     Key features :

     - **Abstraction:**

       They provide a YAML-based specification that defines how a container should run, replacing the complex command-line arguments used in Docker.
     
     - **Encapsulation:**

       While they often hold a single container, a Pod can contain multiple containers that share the same network and storage resources, allowing them to communicate easily.
     
     - **Foundation:**

       A Pod is not a full-featured management tool on its own; it serves as the building block for higher-level abstractions like Deployments, which add essential capabilities such as auto-healing and auto-scaling.


   - **Deployment**
     
     Deployment is a high-level abstraction that acts as a manager for your application, sitting on top of Pods to provide robust orchestration.

     Key features:

     - **Automation:** Unlike manually creating Pods, a Deployment allows you to define the desired state of your application (like the number of replicas), and it automatically ensures that state is maintained.

     - **Auto-healing:**

       If a Pod crashes, the Deployment detects the failure and replaces it to maintain the requested number of instances, ensuring zero downtime.

     - **Auto-scaling:**

       It allows you to easily scale your application up or down by updating the replica count in the YAML configuration, and a ReplicaSet controller handles the creation or deletion of the underlying Pods.
       
     - **Abstraction:**

       By using a Deployment, you do not need to manage individual ReplicaSets or Pods directly; you simply define the template in a YAML file and let the controller handle the lifecycle.
       
   - **ReplicaSet**

     A ReplicaSet is a vital Kubernetes controller designed to guarantee that a specified number of Pod replicas are running at any given time. It serves as the engine behind Deployments.

     Key functions:
     
     - **Maintaining Desired State:**

       It continuously monitors the cluster to ensure the actual state matches the desired replica count defined in your configuration.

     - **Auto-Healing:**

       If a Pod is deleted or crashes, the ReplicaSet immediately detects the discrepancy and initiates the creation of a new replacement to maintain your application's availability.
       
     - **Abstraction:**

       While you can create a ReplicaSet manually, it is typically managed automatically by a Deployment, which acts as a higher-level wrapper for rolling updates and scaling operations.
        
   - **Service**
     
     Service is a critical abstraction that provides load balancing, service discovery, and a stable network endpoint for accessing your applications. Because Pods are ephemeral and frequently change IP addresses, a Service provides a constant, stable IP address and DNS name for clients to connect to your application, regardless of the underlying Pod lifecycle. It intelligently routes incoming network traffic across all the healthy Pods that match its labels and selectors, ensuring high availability and efficient resource usage. Depending on the required reachability, a Service can be configured in different modes, including ClusterIP for internal access, NodePort for external access via a static node port, or LoadBalancer for exposing the application via a cloud-provider load balancer.
     
   - **Ingress**

     Ingress is an API object that manages external access to services within a cluster, typically via HTTP and HTTPS. It acts as a entry point, providing advanced routing capabilities—such as path-based and host-based load balancing—that standard Service types (like NodePort or LoadBalancer) often lack. A critical component of this architecture is the Ingress Controller, which must be deployed in the cluster to actually implement the rules defined in your Ingress resources by monitoring the cluster and updating the underlying load balancer configuration accordingly. By consolidating traffic management, Ingress helps solve the cost and complexity issues associated with exposing multiple services individually through dedicated cloud-provider load balancers.
     
   - **ConfigMap**

     ConfigMap is an API object used to decouple configuration data from containerized application code. It allows you to store non-sensitive information—such as environment variables, database connection details, or configuration files—in a central resource that can be injected into Pods as environment variables or mounted as files within the container's filesystem. By using a ConfigMap, you avoid hardcoding configuration values inside your application, making your images more portable and enabling you to update settings dynamically without needing to rebuild or restart your containers.
     
   - **Secret**
   
   </details>

   
</details>
