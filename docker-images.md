

```markdown
# **📦 Working with Docker Images**  
*Complete guide to building, managing, and deploying containerized applications*

---

## **Table of Contents**  
1. [Docker Images Overview](#-docker-images-overview)  
2. [Pulling from Docker Hub](#-pulling-from-docker-hub)  
3. [Building Custom Images](#-building-custom-images)  
4. [Image Management](#-image-management)  
5. [Docker Hub Integration](#-docker-hub-integration)  
6. [Security Best Practices](#-security-best-practices)  
7. [Troubleshooting](#-troubleshooting)  

---

## **📌 Docker Images Overview**  
Docker images are immutable templates containing:  
✅ Application code  
✅ Runtime environment  
✅ Dependencies  
✅ Configuration files  

**Key Characteristics:**  
- Built from `Dockerfile` instructions  
- Stored as layered filesystem  
- Versioned via tags  

---

## **🔍 Pulling from Docker Hub**  

### **Search for Images**  
```bash
docker search nginx
```

### **Pull Official Images**  
```bash
docker pull nginx:alpine  # Lightweight version
docker pull ubuntu:22.04  # Specific release
```

### **List Local Images**  
```bash
docker images
# OR
docker image ls
```

---

## **🛠️ Building Custom Images**  

### **Sample Dockerfile**  
```dockerfile
# Use official lightweight NGINX
FROM nginx:alpine

# Set working directory
WORKDIR /usr/share/nginx/html

# Copy static content
COPY index.html .

# Expose port
EXPOSE 80

# Runtime command (included in nginx image)
# CMD ["nginx", "-g", "daemon off;"]
```

### **Build Command**  
```bash
docker build -t my-webapp:v1 .
```

### **Run Container**  
```bash
docker run -d -p 8080:80 my-webapp:v1
```

---

## **🗂️ Image Management**  

| Command | Description |  
|---------|-------------|  
| `docker image ls` | List images |  
| `docker image rm` | Remove image |  
| `docker image prune` | Clean unused images |  
| `docker history` | View image layers |  

---

## **🚀 Docker Hub Integration**  

### **1. Tag Your Image**  
```bash
docker tag my-webapp:v1 username/repo:v1
```

### **2. Login to Docker Hub**  
```bash
docker login
```

### **3. Push Image**  
```bash
docker push username/repo:v1
```

---

## **🔐 Security Best Practices**  

1. **Use Minimal Base Images**  
   ```dockerfile
   FROM alpine:3.18  # Instead of ubuntu
   ```

2. **Non-Root User**  
   ```dockerfile
   RUN adduser -D appuser && chown -R appuser /app
   USER appuser
   ```

3. **Scan for Vulnerabilities**  
   ```bash
   docker scan my-webapp:v1
   ```

---

## **⚠️ Troubleshooting**  

| Issue | Solution |  
|-------|----------|  
| Build fails | Check `Dockerfile` syntax |  
| Port not accessible | Verify `-p` flag and security groups |  
| Permission denied | Add user to docker group |  
| Push rejected | Re-authenticate with `docker login` |  

---

## Screenshots

<img width="524" alt="Snipaste_2025-07-10_07-12-34" src="https://github.com/user-attachments/assets/2959dd19-f053-4765-99a4-4607c6bae152" />


<img width="706" alt="Snipaste_2025-07-10_07-12-09" src="https://github.com/user-attachments/assets/32b446bf-c173-4644-8693-bc177987cb5f" />



<img width="461" alt="Snipaste_2025-07-10_07-11-27" src="https://github.com/user-attachments/assets/3e268ac5-2f4e-4d37-90e7-a0ed56dcb71a" />



<img width="599" alt="Snipaste_2025-07-10_07-10-47" src="https://github.com/user-attachments/assets/4da06d22-57b8-4424-9d68-b1dd87b4138a" />


## **📚 Resources**  
- [Docker Official Documentation](https://docs.docker.com/)  
- [Dockerfile Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)  
- [NGINX Docker Guide](https://hub.docker.com/_/nginx)  

[![Docker](https://img.shields.io/badge/Docker-%232496ED.svg?logo=docker)](https://www.docker.com)
```

