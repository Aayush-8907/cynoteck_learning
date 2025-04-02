
## What is Docker? 

- Docker is an **open-source centralized platform** used to **create, deploy, and run applications**. 
- Docker uses **containers** on the host operating system (OS) to run applications.
- It lets applications use the **same Linux kernel** as the system on the host computer, instead of creating a whole virtual OS. 
- We can install Docker on **any OS**, but the Docker engine runs natively on a **Linux distribution**.
- Docker is written in the **Go** language.
- Docker is a tool that does **OS-level virtualisation**, also called **containerization**.

## History and Purpose 
- Docker was first released in **March 2013**. 
- It was developed by **Solomon Hykes** and **Sebastien Pahl**. 
- Docker is a set of **Platform as a Service (PaaS)** tools. 
- It uses **OS-level virtualization**, while virtual machines (VMs) use **hardware-level virtualization**. 
- Before Docker, many users had a problem: code would run on the **developer’s system** but not on the **user’s system**.

## Docker Architecture 
Docker follows a client-server architecture i.e. the client send the request and then the server take the requests and according to that request it give the response.

for e.g.
- **Docker Client** → Sends a request (e.g., `docker run python3.11`).  
- **Docker Daemon (Server)** → Processes the request and runs a container.  
- **Response Sent** → The container starts, and the output is shown.


![[docker architecture.png]]


### **Docker Client** 

The client is responsible for sending the requests to the Docker Daemon (dockerd). It acts as a command line interface for users. 

### **Docker Daemon (`dockerd`) - The Brain of Docker**

The **Docker Daemon** is responsible for handling all tasks requested by the **Docker Client**.

### **How It Works?**

-  **Docker Client sends a request** (e.g., `docker run python:3.11`).  
-  **Docker Daemon (`dockerd`) receives the request** and decides what to do:

- **Pull the image** (if not available).
- **Create a container** from the image.
- **Run the container** and execute the application.  
    - **The container runs**, and the client sees the output.

### **Docker registries**

It is the storage where docker image are stored and pull that image by the docker daemon that client want to make. There are two type of registries
- Private registries - It contains developer image that developer created for there project
- Public registries - It contains all the image that can be used in docker and manged by docker team