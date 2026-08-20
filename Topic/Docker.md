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

**DockerDocker :** DockerDocker is an open-source OS‑level virtualization or containerization platform/tools.

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

- **Dockerfile:**

  A simple text file containing the instructions used to build a Docker image.Docker
  
- **Docker Image:**

  A read-only template/ snapshot  or "blueprint" that contains the application code, libraries, and environment settings needed to run it.
  
- **Docker Container:**

  A live, running instance of an image. It is isolated from other containers and the host system but shares the host's operating system kernel, making it much more lightweight than a virtual machine (VM).


- **Docker Volume:**

  A Docker Volume is a mechanism for provides persistent storage for containers that generated by and used by Docker containers. allowing data to survive beyond the container's lifecycle.

  Docker Volumes are the recommended way to store and manage data in Docker containers.

  Since containers are temporary by nature, any data stored inside a container is lost when the container is removed. Docker Volumes solve this problem by storing data outside the container on the host machine, ensuring the data remains safe and accessible even if the container is stopped, deleted, or recreated.

  

- **Docker Network:**

  Docker networking is the mechanism/feature that allows containers to secure communicate with each other, the host system, and external networks like the internet.

  It provides network isolation and connectivity, allowing containers to securely exchange data and services.

  Each container gets its own isolated network stack, including a virtual NIC (e.g., eth0), IP address, and routing rules. Virtual networks such as bridge and overlay connect containers to the broader container network.

How Docker Networking Works
When you run containers, Docker automatically handles network setup. By default, Docker Compose sets up a default network so containers can discover each other by name (DNS-based service discovery). This means that instead of using IP addresses, one container can reach another simply by referencing the container or service name. 
docs.docker.com

A critical detail: the default bridge network does not resolve container names. This is the root cause of most "can't connect to the database" bugs in Docker. When two containers are placed on Docker's default bridge, they cannot find each other by name — only by IP. 
arnab-k.medium.com

However, user-defined bridge networks do support automatic DNS resolution. Two containers on the same user-defined bridge network can reach each other's listening ports over TCP/IP using container names.




Bridge

(default)
The most common network type. When you start a container without specifying a network, it joins the default bridge network.

A user-defined bridge network is recommended for production, as it provides DNS-based name resolution and better isolation.

Bridged networking maps host.docker.internal through host-gateway, allowing containers to reach the host machine. 
github.com

2.
Host

Removes network isolation between the container and the Docker host. The container shares the host's networking namespace directly (no virtual NIC or separate IP).

3.
None

Completely disables networking for the container. Useful for containers that need maximum isolation.

4.
Overlay

Enables communication between containers running on different Docker hosts (multi-host networking). Essential for Docker Swarm and distributed architectures. Virtual networks like bridge and overlay are the two primary virtual network constructs in container networking. 
cleanstart.com

5.
Macvlan

Assigns a real MAC address to each container, making it appear as a physical device on the network. Useful for legacy applications that expect to be directly connected to the physical network.


  Common Network Types ::
  
  Bridge Network (default): Communication between containers on the same host.

  Host Network: Container shares the host's network.

  Overlay Network: Communication between containers across multiple Docker hosts.

  None Network: Disables networking for the container.
  

- Hub:

  A cloud-based repository where developers can find, share, and store container images.

  ---
  
  
  ---
</details>


  
<details><summary><h3><mark> Docker multi stage build, layer-caching, layer architecture in Docker </mark></h3></summary>
  
  ---
</details>

<details><summary><h3><mark> Docker networking? </mark></h3></summary>

  ---
</details>





