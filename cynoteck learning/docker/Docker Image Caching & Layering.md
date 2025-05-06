
### What is a Layer?

- Every command in the Dockerfile (e.g. `RUN`, `COPY`, `CMD`) creates a new image **layer**.
- Docker **caches** these layers to avoid rebuilding unchanged parts.

### Why Caching is Useful?

- Saves time and compute during repeated builds.
    
- Docker **only rebuilds layers that changed**, and everything **below** them.
    
- If earlier steps are unchanged, Docker **uses cached layers**.

### For example

```
Dockerfile:

FROM ubuntu                    # Layer 1 (Base Image)
RUN apt update                 # Layer 2
RUN apt install python3        # Layer 3
COPY requirements.txt .        # Layer 4
RUN pip install -r requirements.txt  # Layer 5
COPY . .                       # Layer 6
CMD ["python3", "app.py"]      # Layer 7

```

If we **change `requirements.txt`**, Docker will:

- Reuse Layers 1–3 
    
- Rebuild Layers 4–7 