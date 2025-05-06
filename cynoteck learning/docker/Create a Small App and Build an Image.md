 ## 1. **Create the Flask App**

We will create a basic Flask application that displays "Hello, Docker!" when accessed through the browser.

1. **Create a folder** for your project. Example: `hello_docker`
    
2. Inside the folder, create a file called `app.py` with the following code:

```
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return 'Hello Docker!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=8000)

```


## 2. **Create a `Dockerfile`**

Next, we need a `Dockerfile` that defines how to build the Docker image for our app.

1. Inside the same project folder (`hello_docker`), create a file called `Dockerfile`.
    
2. Add the following content to the `Dockerfile`

```
# Use an official Python runtime as a base image
FROM python:3.11

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements.txt file into the container
COPY requirements.txt requirements.txt

# Install the dependencies from the requirements.txt
RUN pip install -r requirements.txt

# Copy the app.py file into the container
COPY app.py app.py

# Expose port 8000 to access the Flask app
EXPOSE 8000

# Run the app when the container starts
CMD ["python", "app.py"]

```

This `Dockerfile` does the following:

- Starts with a Python base image (`python:3.11`).
    
- Sets a working directory inside the container as `/app`.
    
- Copies the `requirements.txt` and `app.py` files into the container.
    
- Installs dependencies (like Flask) using `pip`.
    
- Exposes port `8000` so we can access the app.
    
- Specifies the command to run the app: `python app.py`.

### 3.  **Create a `requirements.txt` File**

```
flask
```

## 4. **Build the Docker Image**

Now that we have the `Dockerfile`, `app.py`, and `requirements.txt` files ready, we can **build** the Docker image.

1. Open the terminal/command line and navigate to the `hello_docker` folder.
    
2. Run the following command to build the Docker image:
    

```
docker build -t hello_docker .

```

This will:

- Use the `Dockerfile` to build the image.
    
- Tag the image as `hello_docker`.
    

## 5. **Run the Docker Container**

Once the image is built, we can run it in a container:

1. Run the following command to start a container from the `hello_docker` image


## 5. **Run the Docker Container**

Once the image is built, you can run it in a container:

1. Run the following command to start a container from the `hello_docker` image:
    

```
`docker run -it -p 8000:8000 hello_docker`
```


This will:

- Start the container interactively (`-it`).
    
- Map port `8000` on your local machine to port `8000` inside the container (`-p 8000:8000`).