# Experiment 8 – Creating and Executing Your First Docker Container

## Title
Creating and Executing Your First Container Using Docker

## Aim
To create and execute a Docker container using a Python program.

---

## Requirements
| Item | Details |
|------|---------|
| Platform | Docker Desktop (Windows / Linux / macOS) |
| Language | Python 3 |
| Base Image | python:latest (from Docker Hub) |
| Files | main.py, Dockerfile |

---

## Introduction
**Docker** is an open-source containerization platform that allows developers to package applications and their dependencies into lightweight, portable containers. Unlike virtual machines, Docker containers share the host OS kernel and are faster to start and more resource-efficient.

Key concepts:
| Term | Description |
|------|-------------|
| **Image** | A read-only template used to create containers |
| **Container** | A running instance of an image |
| **Dockerfile** | A text file with instructions to build an image |
| **Docker Hub** | Public registry for Docker images |

---

## Installation
1. Download Docker Desktop from [https://www.docker.com/](https://www.docker.com/)
2. Install and launch Docker Desktop.
3. Verify installation:
   ```bash
   docker --version
   ```

---

## Program – `main.py`

```python
#!/usr/bin/env python3
print("Docker is magic!")
```

A minimal Python 3 script that prints a message to the console.

---

## Dockerfile

```dockerfile
FROM python:latest
COPY main.py /
CMD [ "python", "./main.py" ]
```

| Instruction | Purpose |
|-------------|---------|
| `FROM python:latest` | Uses the latest official Python image as the base |
| `COPY main.py /` | Copies `main.py` from the host into the container root |
| `CMD [...]` | Runs `main.py` using Python when the container starts |

---

## Build the Docker Image

Navigate to the folder containing `Dockerfile` and `main.py`, then run:

```bash
docker build -t python-test .
```

- `-t python-test` — Tags the image with the name `python-test`
- `.` — Uses the current directory as the build context

---

## Run the Docker Container

```bash
docker run python-test
```

---

## Expected Output

```
Docker is magic!
```

---

## Useful Docker Commands

| Command | Purpose |
|---------|---------|
| `docker images` | List all images on the system |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers (including stopped) |
| `docker rm <id>` | Remove a stopped container |
| `docker rmi <image>` | Remove an image |
| `docker logs <id>` | View container logs |

---

## Files
| File | Description |
|------|-------------|
| `main.py` | Python script executed inside the container |
| `Dockerfile` | Instructions to build the Docker image |
| `output.txt` | Simulated terminal output |

---

## How to Execute
1. Install Docker Desktop.
2. Open a terminal in the folder containing `Dockerfile` and `main.py`.
3. Build: `docker build -t python-test .`
4. Run: `docker run python-test`
5. Observe the output.

---

## Result
The first Docker container was created and executed successfully. The Python script ran inside the container and printed the expected output.
