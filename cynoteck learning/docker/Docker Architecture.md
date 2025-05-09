

![[docker architecture.png]]

Docker works on a **Client-Server Model**.

- You (user) send commands from **Docker Client**.
- Commands go to **Docker Daemon** (brain of Docker).
- Docker Daemon manages:
  - Images
  - Containers
  - Networks & Storage
- It pulls Images from **Docker Registry** (online image storage).

---

## Main Components of Docker

### 1. Docker Client
- It is the tool you use to talk to Docker.
- Example Command:

    - **Private Registries**: Store custom images for specific projects or organizations.
### How It All Works Together

Here’s the complete flow using your example (docker run python:3.11):

1. **Docker Client Sends Request**: You type docker run python:3.11, and the client sends it to the daemon.
2. **Docker Daemon Processes the Request**:
    - Checks if the **image** (python:3.11) exists locally.
    - If not, pulls it from the **registry** (Docker Hub).
    - Uses the **image** to create a **container**.
    - Starts the **container** and executes the default command (e.g., a Python shell).
3. **Response Sent**: The daemon sends the container’s output back to the client, which you see on your screen.
