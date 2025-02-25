# 🐳 Docker Cheatsheet

## 📌 Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Basic Commands](#basic-commands)
- [Container Management](#container-management)
- [Image Management](#image-management)
- [Volumes & Storage](#volumes--storage)
- [Networking](#networking)
- [Docker Compose](#docker-compose)
- [Dockerfile](#dockerfile)
- [Advanced Usage](#advanced-usage)

---

## 🔹 Introduction
Docker is a containerization platform that allows you to develop, ship, and run applications in isolated environments called **containers**.

---

## 📥 Installation
### 🔹 Install Docker
[Official Docker Installation Guide](https://docs.docker.com/get-docker/)

### 🔹 Verify Installation
```sh
$ docker --version
# Example Output: Docker version 24.0.0, build abcdef1
```

---

## 🚀 Basic Commands
### 🔹 Check Docker Version
```sh
$ docker version
```

### 🔹 Display System Info
```sh
$ docker info
```

### 🔹 Pull an Image 🏗️
```sh
$ docker pull ubuntu
```

### 🔹 Run a Container 📦
```sh
$ docker run -it ubuntu bash
```
**Explanation:**
- `-i` → Interactive mode
- `-t` → Allocate a pseudo-TTY
- `ubuntu` → Image name
- `bash` → Command to execute

### 🔹 List Running Containers 🚢
```sh
$ docker ps
```

### 🔹 List All Containers 🗂️
```sh
$ docker ps -a
```

### 🔹 Stop a Running Container 🛑
```sh
$ docker stop <container_id>
```

### 🔹 Remove a Container 🗑️
```sh
$ docker rm <container_id>
```

---

## 📦 Container Management
### 🔹 Start a Stopped Container 🚀
```sh
$ docker start <container_id>
```

### 🔹 Restart a Container 🔄
```sh
$ docker restart <container_id>
```

### 🔹 Execute Command in Running Container 🛠️
```sh
$ docker exec -it <container_id> bash
```

---

## 🎭 Image Management
### 🔹 List Images 🖼️
```sh
$ docker images
```

### 🔹 Remove an Image 🗑️
```sh
$ docker rmi <image_id>
```

### 🔹 Build an Image 🏗️
```sh
$ docker build -t my_image .
```

---

## 📂 Volumes & Storage
### 🔹 Create a Volume 📦
```sh
$ docker volume create my_volume
```

### 🔹 List Volumes 📜
```sh
$ docker volume ls
```

### 🔹 Remove a Volume 🗑️
```sh
$ docker volume rm my_volume
```

### 🔹 Mount a Volume 🏗️
```sh
$ docker run -v my_volume:/data -it ubuntu bash
```

---

## 🌐 Networking
### 🔹 List Networks 🌍
```sh
$ docker network ls
```

### 🔹 Create a Network 🔧
```sh
$ docker network create my_network
```

### 🔹 Connect a Container to a Network 🖧
```sh
$ docker network connect my_network <container_id>
```

### 🔹 Disconnect a Container from a Network ❌
```sh
$ docker network disconnect my_network <container_id>
```

---

## 🏗️ Docker Compose
### 🔹 Install Docker Compose 🛠️
[Installation Guide](https://docs.docker.com/compose/install/)

### 🔹 Example `docker-compose.yml`
```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: password
```

### 🔹 Run Compose 🚀
```sh
$ docker-compose up -d
```

### 🔹 Stop Compose Services 🛑
```sh
$ docker-compose down
```

---

## 📜 Dockerfile
### 🔹 Basic Example
```dockerfile
# Use base image
FROM ubuntu:latest

# Set working directory
WORKDIR /app

# Copy files
COPY . .

# Run command
CMD ["echo", "Hello, Docker!"]
```

### 🔹 Build and Run 🚀
```sh
$ docker build -t my_app .
$ docker run my_app
```

---

## ⚡ Advanced Usage
### 🔹 Limit CPU & Memory 🖥️
```sh
$ docker run --memory="512m" --cpus="1" ubuntu
```

### 🔹 Run in Detached Mode 🏃‍♂️
```sh
$ docker run -d nginx
```

### 🔹 Inspect Logs 📝
```sh
$ docker logs <container_id>
```

### 🔹 Prune Unused Data 🧹
```sh
$ docker system prune -a
```

---

## 🎯 Conclusion
This **Docker Cheatsheet** provides a quick reference for common Docker commands and concepts. Mastering these will help you efficiently manage containers, images, volumes, and networks.

🚀 **Happy Dockering!** 🐳
