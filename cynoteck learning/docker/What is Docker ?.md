**Docker** is an open platform for developing, shipping, and running applications. It does this using **containers**, which contains all the necessary dependencies like libraries, and code that is required for run an application.

**Here’s how Docker fits into development:**

- **Containers**: These are lightweight, portable, and isolated environments (container can run independently without interfering with other container. For e.g. - one container contains python 3.11 and second container contains 3.10)
- **CI/CD Integration**: Docker is often used in **CI/CD pipelines** to automate testing, deployment, and rollback processes.
- **Error Handling & Redeployment**: If an error occurs in a test environment, developers can fix the issue, rebuild the container, and redeploy without affecting other applications.
- **Collaboration**: Docker containers can be shared with teammates using **Docker Hub** or private registries, making it easy to distribute and collaborate on applications.


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