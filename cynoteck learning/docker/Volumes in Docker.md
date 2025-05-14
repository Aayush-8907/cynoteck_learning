
A **Volume** is a special place to store data **outside** the container, so the data is not lost when:

- The container stops
    
- The container is deleted
    
- You rebuild the contain

### Why Use Volumes?

- Containers are temporary; when deleted, they lose data
    
- Code doesn’t change often, but **data** (like database or user uploads) **does**
    
- Volumes keep the important data safe


### Type of Volumes

 ## **1. Named Volumes** 

- **Definition**: Volumes managed entirely by Docker.
    
- **Use Case**: When you don’t care about the exact host path — just want Docker to store and manage data.

```
services:
  app:
    volumes:
      - my_named_volume:/app/data

volumes:
  my_named_volume:

```


## 2. **Bind Mounts**

- **Definition**: Direct mapping between a **specific path** on the host and a **path inside** the container.
    
- **Use Case**: When you want to access local files inside a container — great for **code development**, live file editing, or using an existing database.

```
services:
  app:
    volumes:
      - ./data:/app/data

```

- `./data` is the **host machine’s path**.
    
- `/app/data` is the **container’s path**.

## 3. **tmpfs Mounts** (Temporary Storage in Memory)

- **Definition**: Creates a temporary file system in the container’s memory (RAM).
    
- **Use Case**: For **sensitive** or **temporary** data (like passwords, session caches, etc.).
    
- **Data is lost** when the container stops.

```
services:
  app:
    image: my_app
    tmpfs:
      - /app/cache

```

