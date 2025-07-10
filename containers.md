

```markdown
# **🐳 Working with Docker Containers**  
*Complete guide to container lifecycle management and operations*

---

## **Table of Contents**  
1. [Container Basics](#-container-basics)  
2. [Running Containers](#-running-containers)  
3. [Lifecycle Management](#-lifecycle-management)  
4. [Practical Operations](#-practical-operations)  
5. [Best Practices](#-best-practices)  
6. [Troubleshooting](#-troubleshooting)  

---

## **📌 Container Basics**  
Docker containers are:  
✅ Lightweight executable packages  
✅ Isolated from host and other containers  
✅ Ephemeral by default  

**Key Characteristics:**  
- Created from images  
- Have unique IDs/names  
- Can be paused, restarted, or removed  

---

## **🚀 Running Containers**  

### **Basic Execution**  
```bash
docker run ubuntu  # Runs container in foreground
docker run -d ubuntu  # Detached mode (background)
```

### **Common Options**  
| Flag | Purpose | Example |  
|------|---------|---------|  
| `-e` | Set env vars | `-e "APP_ENV=prod"` |  
| `-p` | Port mapping | `-p 8080:80` |  
| `-v` | Volume mount | `-v /data:/app/data` |  
| `--name` | Assign name | `--name my_container` |  

### **Interactive Session**  
```bash
docker run -it ubuntu bash  # Interactive terminal
```

---

## **🔄 Lifecycle Management**  

### **Core Commands**  
| Command | Action |  
|---------|--------|  
| `docker start` | Start stopped container |  
| `docker stop` | Graceful shutdown |  
| `docker restart` | Stop + start |  
| `docker pause` | Freeze processes |  
| `docker unpause` | Resume processes |  

### **Example Workflow**  
```bash
# Start container
docker run -d --name webapp nginx

# Check status
docker ps

# Stop container
docker stop webapp

# Restart
docker restart webapp
```

---

## **🧰 Practical Operations**  

### **Viewing Containers**  
```bash
docker ps       # Running containers
docker ps -a    # All containers (including stopped)
docker stats    # Live resource usage
```

### **Removing Containers**  
```bash
docker rm container_id      # Remove stopped container
docker rm -f container_id   # Force remove running container
docker container prune      # Remove all stopped containers
```

### **Inspecting Containers**  
```bash
docker logs container_id    # View output
docker inspect container_id # Detailed config
docker exec -it container_id bash # Enter running container
```

---

## **🏆 Best Practices**  

1. **Always Name Containers**  
   ```bash 
   docker run --name webapp -d nginx
   ```

2. **Clean Up Regularly**  
   ```bash
   docker system prune
   ```

3. **Use Stop Before Remove**  
   ```bash
   docker stop webapp && docker rm webapp
   ```

4. **Limit Resource Usage**  
   ```bash
   docker run -m 512m --cpus 1.5 myapp
   ```

---

## **⚠️ Troubleshooting**  

| Issue | Solution |  
|-------|----------|  
| Container exits immediately | Check logs with `docker logs` |  
| Port conflict | Verify host port isn't in use |  
| Permission errors | Use `--privileged` for testing |  
| Missing container | Check `docker ps -a` |  

---

## **🔧 Hands-On Task**  

### **Container Operations Challenge**  
1. **Launch Ubuntu Container**  
   ```bash
   docker run -it --name my_ubuntu ubuntu bash
   ```

2. **Run System Check**  
   ```bash
   uname -a
   exit
   ```

3. **Stop and Verify**  
   ```bash
   docker stop my_ubuntu
   docker ps -a | grep my_ubuntu
   ```

4. **Restart and Cleanup**  
   ```bash
   docker start my_ubuntu
   docker rm -f my_ubuntu
   ```

---

## Screenshots

<img width="467" alt="Snipaste_2025-07-10_07-26-24" src="https://github.com/user-attachments/assets/702baae5-d39d-4ee8-bb8a-eadd9d3913c8" />


<img width="1010" alt="Snipaste_2025-07-10_07-25-47" src="https://github.com/user-attachments/assets/1b3ac3ea-01e0-4c98-8cd1-7a231582ffde" />


<img width="457" alt="Snipaste_2025-07-10_07-25-11" src="https://github.com/user-attachments/assets/b9e25799-1bae-4511-ab5d-5cafec364374" />


<img width="850" alt="Snipaste_2025-07-10_07-24-19" src="https://github.com/user-attachments/assets/0fd62695-e362-403e-972c-9cade392e35a" />


<img width="588" alt="Snipaste_2025-07-10_07-23-36" src="https://github.com/user-attachments/assets/8d857288-5aa8-4521-8e4a-c5a72d5c6ecf" />


<img width="619" alt="Snipaste_2025-07-10_07-23-07" src="https://github.com/user-attachments/assets/d5a344b3-cfaf-438c-8970-bc89296bdec7" />


## **📚 Resources**  
- [Docker Run Reference](https://docs.docker.com/engine/reference/run/)  
- [Container Lifecycle Docs](https://docs.docker.com/engine/reference/commandline/container/)  

[![Docker](https://img.shields.io/badge/Docker-%232496ED.svg?logo=docker)](https://www.docker.com)
```

