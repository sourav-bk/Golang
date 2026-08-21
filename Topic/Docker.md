<details><summary><h3><mark>Docker vs. Virtual Machines (VM)</mark></h3></summary>
  
The core difference lies in architecture: **VMs virtualize hardware**, while **Docker virtualizes the operating system**.

Docker and Virtual Machines both provide environments to run applications, but they differ mainly in how they use system resources and isolate processes

**Virtual Machine (VM)** runs a full operating system on top of a hypervisor, meaning each VM includes its own guest OS, binaries, and libraries, making it heavier, slower to start, and more resource-intensive, but offering strong isolation and the ability to run different OS types on the same hardware; 

**Docker** uses containerization, where containers share the host OS kernel and package only the application along with its dependencies, making them lightweight, faster to start, highly portable, and efficient in resource usage, though they provide comparatively less isolation than VMs since they rely on the host OS.

---

## Quick Comparison


| Feature | Docker (Containers) | Virtual Machine (VM) |
| :--- | :--- | :--- |
| **Architecture** | Shares host OS kernel | Full guest OS per instance |
| **Startup Speed** | Milliseconds to seconds | Minutes (full OS boot) |
| **Resource Use** | Lightweight (shared RAM/CPU) | Heavyweight (dedicated allocation) |
| **Isolation** | Process-level (less secure) | Hardware-level (more secure) |
| **Size** | Megabytes | Gigabytes |
| **Portability** | High (runs anywhere with Docker) | Moderate (tied to hypervisor) |

---

## Docker (Containers)
Docker uses a container engine to isolate applications. 

* **How it works**: Packages code and dependencies together. Shares the host OS kernel.
* **Best for**: Microservices, fast scaling, and continuous deployment.
* **Pros**: Highly efficient, fast, uses fewer resources.
* **Cons**: Shared kernel means lower isolation; restricted to host OS type.

## Virtual Machines (VMs)
VMs use a hypervisor to slice up physical hardware.

* **How it works**: Simulates a complete computer. Runs a full, independent guest OS.
* **Best for**: Deep isolation, legacy apps, and running different operating systems.
* **Pros**: Full security isolation, runs any OS on any hardware.
* **Cons**: Slow to boot, heavy resource consumption, large file sizes.

---

## Hybrid Approach
You can **run Docker inside a VM**. This combines the hardware-level security of a VM with the speed and agility of Docker containers

---
</details>



<details><summary><h3><mark> Docker | Containerization | container | Architecture </mark></h3></summary>

**Docker :** Docker is an open-source OS‑level virtualization or containerization platform/tools.

**Containerization :** Containerization is a software deployment process that allows developers to package applications and all their dependencies(such as libraries, configurations, and runtime) into a single-lightweight unit, that called a container.

which allows applications to share the host OS kernel instead of running a separate guest OS like in traditional virtualization.
This design makes Docker containers lightweight, fast, and portable, while keeping them isolated from one another.

Think of it as a "shipping container" for software: it ensures that  application runs exactly the same way, whether it's on run on local  server, or a cloud platform.

---

***Core Architectural Components ::***

Docker Core Architecture have 3 core Components - **1. Docker Client | 2. Docker Host / Docker Daemon | 3. Docker Registries**

Docker uses a client–server architecture. The Docker-client talks to the Docker-Daemon, which builds, runs, and manages containers. They communicate through a REST API via UNIX sockets or a network interface.

<img alt="maxresdefault" width="800" src="https://github.com/user-attachments/assets/32211ef0-9de9-44eb-8d39-916fec0b2bfb" />

- **Docker Client :**
  
  The Docker client is the primary interface used to interact with the Docker ecosystem. It provides both a command-line interface (CLI), known as the **Docker-CLI**, and a graphical user interface (GUI) through **Docker-Desktop**, enabling users to manage containers, images, and other Docker resources efficiently.
  
- **Docker Daemon :**
  
  The Docker-Daemon is the core background service responsible for managing Docker containers, images, networks, and volumes. It listens for Docker API requests which coming from Docker-Client ( like from Docker-CLI or Docker-Desktop ) and performs the actual work of building, running, and managing containers or Orchestrating the entire lifecycle of Docker-containers. Docker-Daemon can also communicate with other Daemons to manage Docker services.

- **Docker Registries :**

  A Docker Registry is a centralized storage and distribution system for Docker images. It allows users to store, share, and manage container images.
  **Docker Hub** is a public registry that anyone can use, and Docker is configured to look for images on Docker Hub by default. We can even run our own private registry.
  
  When we use the `docker pull` or `docker run` commands, the required images are pulled from configured registry. and When we use the `docker push` command, the image is pushed to configured registry.
  
  ---
  
</details>


<details><summary><h3><mark> Docker Container Lifecycle Management </mark></h3></summary>
  
  Lifecycle of Docker container consists of five states:
  
  **1. Created state | 2. Running state | 3. Paused/unpaused state | 4. Stopped state | 5. Killed/Deleted state**

  <img alt="image" width="450" src="https://github.com/user-attachments/assets/6585623d-c5bd-48a9-9457-73e360eaa1f3" />

  
1. **Created state ::** container is created from a Docker image but the main application process hasn't started yet.

   > we create container using
   > 
   > docker create --name <container_name> <image_name>

2. **Running state ::** container executes the main commands that specified in the image. Resources like CPU and memory are actively allocated.
   
   > we Start container FROM Running state
   > 
   > docker create --name <container_name> <image_name>
   >
   > (Start)  docker create --name <container_name> <image_name> | docker start <container_name>
   >
   > (Create + Start) docker run --name <container_name> <image_name>
   

3. **Paused/unpaused state ::** A container whose processes have been paused / or Freezes all processes but Memory is not released. Similar to putting laptop on sleep mode.

   > we create container into Running state
   > 
   > docker pause <container_name>   |   docker unpause <container_name>

4. **Stopped state ::** Container is not running. No CPU is being used by the container. Container's filesystem still exists and configuration is preserved. we can start it again.

   > we can Stopped Running state container using
   >  
   > docker stop <Running_container_name>

5. **Killed/Deleted state ::** Container is removed from the engine or orchestrator. All its un-persisted resources are released and Container no longer exists on system.
   
   > we can KILL/DELETE Running state container using
   > 
   > docker kill <Running_container_name>
   >
   > docker rm -f <Running_container_name>

  
</details>


<details><summary><h3><mark>Components of Docker</mark></h3></summary>
  
  ***Components of Docker ::***

- **Dockerfile :**

  A simple text file containing the instructions used to build a Docker image.

  ---
  
- **Docker Image :**

  A read-only template/ snapshot  or "blueprint" that contains the application code, libraries, and environment settings needed to run it.

  ---
  
- **Docker Container :**

  A live, running instance of an image. It is isolated from other containers and the host system but shares the host's operating system kernel, making it much more lightweight than a virtual machine (VM).

  ---

- **Docker Volume :**

  A Docker Volume is a mechanism for provides persistent storage for containers that generated by and used by Docker containers. allowing data to survive beyond the container's lifecycle.

  Docker Volumes are the recommended way to store and manage data in Docker containers.

  Since containers are temporary by nature, any data stored inside a container is lost when the container is removed. Docker Volumes solve this problem by storing data outside the container on the host machine, ensuring the data remains safe and accessible even if the container is stopped, deleted, or recreated.

  ---
  
- **Docker Network :**

  Docker networking is the mechanism/feature that allows containers to secure communicate with each other, the host system, and external networks like the internet.

  It provides network isolation and connectivity, allowing containers to securely exchange data and services.

  Each container gets its own isolated network stack, including a virtual NIC (e.g., eth0), IP address, and routing rules. Virtual networks such as bridge and overlay connect containers to the broader container network.
  
  ---

  **How Docker Networking Works**

  Docker networking is built/internally uses on top of core Linux primitives: network namespaces, virtual Ethernet (veth pairs) , Bridges, and NAT rules. Together, these provide containers with isolated yet connected networking.

  Each container receives its own network stack — a virtual NIC (eth0), a private IP address, and its own routing table. Virtual networks such as bridge and overlay connect containers to one another and to the outside world.

  **Docker Networking Components ——————** 1. Network Namespace, 2. Virtual Ethernet (Pair veth), 3. Docker Bridge, 4. NAT (Network Address Translation), 5. Port Mapping

  <details><summary><mark>More</mark></summary>   
    
    1. Network Namespace ::

       Each container runs inside its own **network namespace**, completely isolated from the host and other containers.

       Container is own  Network interfaces, IP address, Routing table, DNS configuration, Firewall rules.

       From inside the container, it looks like the container has its own independent network stack.

    2. Virtual Ethernet (Pair veth) ::

       Docker uses a virtual Ethernet pair (also called **veth pair** ) to connect Container to the host network.

       We can think like, **veth pair** like a virtual network cable.

       This allows traffic to move between the container and the Docker network.
    
    3. Docker Bridge ::

       By default, Docker creates the virtual bridge (also called **docker0** )

       The **Bridge** works like a virtual switch. It allows containers attached to the same bridge network to communicate with each other over private subnet.

       For user-defined bridge networks, Docker also provides built-in DNS resolution so containers can communicate using names.

    4. NAT (Network Address Translation) ::

       When container access the internet, Docker uses NAT through Linux iptables rules that translate the container's private IP to the host's public IP on outbound traffic.

       Container (172.17.0.2) → docker0 bridge → iptables (MASQUERADE) → Host machine IP → Internet.

       NAS translates the container’s private IP address into the host machine’s IP address.

    5. Port Mapping ::

       Containers are network-isolated by default. Even if an application inside a container listens on a port, that port is not automatically accessible from outside the container.

       To expose a container port, we publish it using port mapping.

       >docker run -p 8080:80 <image_name>

  </details>   

  **Docker Network Types**

  Depending on how containers need to communicate. Docker provides different network types (also called network drivers).

  Mainly have 3 type ————  1. Bridge Network(default)  2. Host Network 3.  None Network

  <details><summary><mark>More</mark></summary>

   - **Bridge Network(default) ——**

     The most common network type. When WE start a container without specifying a network, it joins the default bridge network.

     It provides DNS-based name resolution and better isolation.

     Bridged networking maps host docker internal through host-gateway, allowing containers to reach the host machine.

   - **Host Network ——**

     Removes network isolation between the container.

     The container shares the host's networking namespace directly (no virtual NIC or separate IP) for communication.

   - **None Network ——**

     Completely disables networking for the container. Useful for containers that need maximum isolation.

  </details>
  
  but also have more 2 type ————   4. Overlay Network 5. Macvlan Network

  <details><summary><mark>More</mark></summary>
    
    - **Overlay Network ——**

      Enables communication between containers running on different Docker hosts (multi-host networking). Essential for multi-Docker-host and distributed architectures.

    - **Macvlan Network ——**

      Assigns a real MAC address to each container, making it appear as a physical device on the network. Useful for legacy applications that expect to be directly connected to the physical network.

  </details>
  
  ---
</details>


  
<details><summary><h3><mark> layer-caching, layer architecture in Docker </mark></h3></summary>
  
  **Docker Layer Architecture**
  Docker Layer Architecture is the method Docker uses to build images in multiple layers. Each instruction in Dockerfile (such as FROM, RUN, or COPY) creates a separate read-only layer. These layers are stacked on top of each other to form a complete Docker image. When a container is created from the image, Docker adds a writable layer on top where all runtime changes are stored.
  
  **Docker Layer Caching**
  Docker Layer Caching is a feature that improves build performance by reusing previously created layers. During an image build, Docker checks whether a layer and its dependencies have changed. If there are no changes, Docker uses the cached version of that layer instead of rebuilding it, which significantly reduces build time.
  
  Both concepts are closely related... Docker's layer architecture provides the foundation for layer caching. Since images are built layer by layer, Docker can identify unchanged layers and reuse them from the cache. In simple terms, layer architecture defines how Docker images are structured, while layer caching utilizes that structure to make image builds faster and more efficient.
  
  **Interview Summary:**
  
  Docker Layer Architecture is the layered design of Docker images where each Dockerfile instruction creates a separate layer. Docker Layer Caching is the mechanism that reuses these existing layers during subsequent builds when no changes are detected. Layer architecture creates the layers, and layer caching leverages them to optimize build speed and resource usage.
  
  ---
</details>

<details><summary><h3><mark> Docker multi stage build </mark></h3></summary>
  
  Docker Multi-Stage Build is a feature that allows multiple FROM statements within a single Dockerfile. It separates the build stage from the runtime stage, enabling Docker to keep only the files required to run the application in the final image.
  
  In a traditional Docker build, the final image often contains source code, build tools, compilers, and dependencies, which increases image size and security risks. With a multi-stage build, the application is compiled or packaged in one stage, and only the final executable or required artifacts are copied to the runtime stage.
  
  As a result, the final Docker image becomes smaller, more secure, and more efficient, since unnecessary build tools and source files are excluded.
  
  **Interview Summary:**
  
  Docker Multi-Stage Build is a technique that uses multiple FROM statements in a Dockerfile to separate the build environment from the runtime environment. The application is built in one stage, and only the necessary artifacts are copied to the final image, resulting in smaller, more secure, and optimized Docker images.

  ```xml

  # Build Stage
  FROM golang:1.22 AS builder
  WORKDIR /app
  COPY . .
  RUN go build -o myapp
  
  # Runtime Stage
  FROM alpine:latest
  COPY --from=builder /app/myapp /myapp
  CMD ["/myapp"]

  ```
  

  ---
</details>
