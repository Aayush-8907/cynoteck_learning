Docker Compose is a tool that lets you define and run **multi-container** Docker applications using a `.yml` file.

Instead of running one container at a time using `docker run`, Compose lets you manage everything together.

### Why Use Docker Compose?

- Run multiple containers (e.g., Flask + SQLite or Flask + PostgreSQL)
    
- Define settings like **ports**, **volumes**, and **environment variables** in one file
    
- Start all containers with just one command:

```
docker compose up --build

```

Example `docker-compose.yml`

```
services:
  flask_app:
    build: .
    ports:
      - "8000:5000"
    volumes:
      - ./responses.db:/app/responses.db
    environment:
      - GROQ_API_KEY=gsk_your_key_here

```

