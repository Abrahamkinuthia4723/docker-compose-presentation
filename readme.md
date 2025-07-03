
## 📌 What is Docker Compose?

**Docker Compose** is a powerful tool for defining and running multi-container Docker applications. It simplifies the deployment of complex service stacks into a single command, streamlining development workflows.

---

##  Why Use Docker Compose? 

Imagine your app needs:

- A **web server**
- A **database**
- **etc...**

Without Docker Compose, you'd have to start each container manually — and remember how to connect them, set ports, link volumes, etc.

---

### 🛠️ Docker Compose helps by:

1) Starting everything with just **one command**  
2) Making sure containers can **talk to each other**  
3) Keeping setup in **one easy-to-read file**  
4) Making it easy to **share or restart** your setup


## 🧾 What is YAML?

**YAML** stands for **"YAML Ain't Markup Language"**  
It is a **human-readable data format** used to describe configuration in a structured way.

---

### 📌 Key Features of YAML

- Easy to read and write (clean syntax)
- Uses indentation instead of brackets or braces
- Commonly used for:
  - Docker Compose (`docker-compose.yaml`)
  - Kubernetes configuration
  - GitHub Actions workflows
  - CI/CD pipeline definitions

## 🐳 Example `docker-compose.yaml` File

Below is a sample Docker Compose file that sets up a Node.js app and a BusyBox container, both connected to the same custom bridge network.

```yaml
version: '3.7'

services:

  node-app:
    container_name: container-ya-node
    build:
      context: .
    image: image-itaunda-node
    ports:
      - "8000:8000"
    networks:
      - network-yangu
    volumes:
      - ./app:/app

  busybox:
    container_name: container-from-registry-busybox
    image: busybox
    command: tail -f /dev/null
    ports:
      - "3000:3000"
    networks:
      - network-yangu

networks:
  network-yangu:
    driver: bridge

volumes:
  my-own-volume: {}
```
---

## key parts of a docker-compose.yaml

| **Section**       | **Purpose**                                                 |
|-------------------|-------------------------------------------------------------|
| `version`         | Compose file format version                                 |
| `services`        | Define containers to run                                    |
| `build`           | How to build image from Dockerfile                          |
| `image`           | Name of the built or pulled image                           |
| `ports`           | Exposes container port to host                              |
| `volumes`         | Mounts local folders or persistent data                     |
| `networks`        | Connects containers so they can talk to each other          |
| `container_name`  | Custom name for easier management                           |

---

##  Essential Docker Compose Commands

| Command | Description |
|--------|-------------|
| `docker-compose up` | Starts all services defined in `docker-compose.yml`. |
| `docker-compose down` | Stops and removes **services**, **networks**, and **volumes** created by `up`. |
| `docker-compose build` | Builds or rebuilds service **images**. |
| `docker-compose ps` | Lists the **status** of running services. |
