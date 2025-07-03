
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

---

##  Essential Docker Compose Commands

| Command | Description |
|--------|-------------|
| `docker-compose up` | Starts all services defined in `docker-compose.yml`. |
| `docker-compose down` | Stops and removes **services**, **networks**, and **volumes** created by `up`. |
| `docker-compose build` | Builds or rebuilds service **images**. |
| `docker-compose ps` | Lists the **status** of running services. |
