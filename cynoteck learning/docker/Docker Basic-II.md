### 1. `FROM`

- **What it does:** Sets the base image for your Docker container.
    
- **Example:**

```
FROM python:3.11
```

### 2. `WORKDIR`

- **What it does:** Sets the working directory inside the container
- Example:

```
WORKDIR /app

```

### 3. `COPY`

- **What it does:** Copies files/folders from your host to the container.
    
- **Example:**

```
COPY requirements.txt requirements.txt
COPY app.py app.py

```

### 4. `ADD`

- **What it does:** Similar to `COPY`, but also supports:
    
    - Automatically extracting archives (.tar, .gz)
- Example:  

```
ADD archive.tar.gz /app/

```

### 5. `RUN`

- **What it does:** Executes a command _while building the image_.
    
- **Example:**

```
RUN pip install -r requirements.txt

```

### 6. `CMD`

- **What it does:** Tells Docker what to run when a container **starts**.
    
- **Override:** You can override this when running the container.
    
- **Example:**
    
```
CMD ["python", "app.py"]

```

### 7. `ENTRYPOINT`

- **What it does:** Defines a fixed main command to run (usually not overridden).
    
- **Example:**

```
ENTRYPOINT ["python"]
CMD ["app.py"]

```


### 8. `ENV`

- **What it does:** Sets environment variables in the container.
    
- **Use case:** Keys, secrets, API URLs.
    
- **Example:**

```
ENV API_KEY=abc123

```

