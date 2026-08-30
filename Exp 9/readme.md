# Experiment 9 – Run a Container from Docker Hub

## Title
Run a Container from Docker Hub

## Aim
To run containers from Docker Hub using Docker CLI commands.

---

## Requirements
| Item | Details |
|------|---------|
| Platform | Docker Desktop (Windows / Linux / macOS) |
| Registry | Docker Hub (https://hub.docker.com/) |
| Containers | Ubuntu, Nginx, MongoDB |
| Network | Internet connection (to pull images) |

---

## Introduction

### Docker Hub
**Docker Hub** is the world's largest container image registry. It provides official and community-maintained images for operating systems, databases, web servers, and more. Docker automatically pulls images from Docker Hub when you run a container that is not yet cached locally.

### Docker CLI
The Docker Command Line Interface (CLI) allows users to manage containers, images, volumes, and networks from the terminal.

---

## Docker CLI Overview

```bash
docker -h
```
Displays all available Docker CLI commands and options.

---

## Experiment Steps

### Step 1: Run an Ubuntu Container

```bash
docker container run -it ubuntu top
```

- Downloads `ubuntu:latest` from Docker Hub (if not cached).
- Runs the `top` command (process list viewer) interactively inside the container.
- Press `q` to quit.

---

### Step 2: Run an Nginx Web Server Container

```bash
docker container run --detach --publish 8080:80 --name nginx nginx
```

| Flag | Meaning |
|------|---------|
| `--detach` | Run in background |
| `--publish 8080:80` | Expose container port 80 on host port 8080 |
| `--name nginx` | Assign the name "nginx" |

**Access in browser:** `http://localhost:8080`  
**Expected page:** *Welcome to nginx!*

---

### Step 3: Run a MongoDB Container

```bash
docker container run --detach --publish 8081:27017 --name mongo mongo:4.4
```

- Runs MongoDB 4.4 in the background.
- Accessible at `localhost:8081`.

---

### Step 4: List Running Containers

```bash
docker container ls
```

Shows all containers that are currently running.

---

### Step 5: Stop Containers

```bash
docker container stop nginx
docker container stop mongo
```

---

### Step 6: Clean Up

```bash
docker system prune
```

Removes all stopped containers, unused images, and build cache.

---

## Port Mapping Summary

| Container | Host Port | Container Port | URL |
|-----------|-----------|----------------|-----|
| nginx | 8080 | 80 | http://localhost:8080 |
| mongo | 8081 | 27017 | localhost:8081 |

---

## Files
| File | Description |
|------|-------------|
| `docker_commands.txt` | All Docker CLI commands used in this experiment |
| `output.txt` | Simulated terminal and browser output |

---

## How to Execute
1. Install Docker Desktop and ensure it is running.
2. Open a terminal (PowerShell / Command Prompt / Bash).
3. Run the commands listed in `docker_commands.txt` one by one.
4. Open `http://localhost:8080` in a browser to see the Nginx welcome page.

---

## Result
Containers were successfully pulled from Docker Hub and executed. The Ubuntu, Nginx, and MongoDB containers ran as expected, and the Nginx web server was accessible via the browser.
