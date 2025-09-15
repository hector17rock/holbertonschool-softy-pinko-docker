# 🐳 Docker Project - Softy Pinko Application

A comprehensive Docker-based web application project demonstrating containerization, microservices architecture, and horizontal scaling. This project implements a full-stack web application with a Flask backend API, Nginx frontend server, and load-balancing proxy server.

## 📸 Project Preview

<div align="center">

![Docker Project Preview](https://via.placeholder.com/800x400/0db7ed/FFFFFF?text=🐳+Docker+Microservices+Project)

***A scalable containerized web application with Flask backend, Nginx frontend, and load-balanced proxy server***

</div>

### 🎬 What You'll Build

| 🎨 Component | 📝 Description | 🚀 Technology |
|-----------|-------------|-------------|
| 🌐 **Frontend** | Responsive Softy Pinko website | Nginx + HTML/CSS/JS |
| 🔗 **Backend API** | RESTful API service | Python Flask |
| 🐳 **Containers** | Isolated, scalable services | Docker + Docker Compose |
| 📊 **Load Balancer** | Distributes traffic efficiently | Nginx Reverse Proxy |

### 🗺️ Project Flow
```
💻 Client Request → 🔄 Nginx Proxy → 📈 Load Balancer → 🐍 Flask APIs (x2+) → 📎 Response
```

> **💡 Quick Demo**: Run `docker-compose up --scale back-end=3` to see horizontal scaling in action!
>
> **📁 Note**: *Add your own screenshots to `/images/` directory - see [images/README.md](./images/README.md) for guidelines*

## 📋 Table of Contents

- [🌟 Project Overview](#project-overview)
- [🏗️ Architecture](#architecture)
- [🔧 Prerequisites](#prerequisites)
- [📂 Tasks Overview](#tasks-overview)
- [🚀 Quick Start](#quick-start)
- [📝 Detailed Task Descriptions](#detailed-task-descriptions)
- [💡 Usage Examples](#usage-examples)
- [🧪 Testing](#testing)
- [🔧 Troubleshooting](#troubleshooting)
- [🌐 Network Architecture](#network-architecture)
- [📊 Performance Considerations](#performance-considerations)
- [🔐 Security Considerations](#security-considerations)
- [📈 Future Enhancements](#future-enhancements)
- [🤝 Contributing](#contributing)
- [📄 License](#license)

## 🌟 Project Overview {#project-overview}

This project demonstrates the evolution of a simple containerized application into a scalable microservices architecture. Starting with a basic "Hello, World!" container, it progresses through:

- 🐍 Backend API development with Flask
- 🌐 Frontend integration with Nginx
- ⚡ Dynamic content loading with AJAX
- 📦 Docker Compose orchestration
- 🔄 Reverse proxy implementation
- 📈 Horizontal scaling with load balancing

## 🏗️ Architecture {#architecture}

The final architecture (Task 6) consists of:

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│                 │    │                  │    │                 │
│   Client Web    │    │  Nginx Proxy     │    │ Flask Backend   │
│   Browser       ├────┤  Load Balancer   ├────┤ API Servers     │
│   (Port 80)     │    │  (Port 80)       │    │ (Multiple)      │
│                 │    │                  │    │                 │
└─────────────────┘    └──────────────────┘    └─────────────────┘
                                │
                                │
                       ┌──────────────────┐
                       │                  │
                       │ Nginx Frontend   │
                       │ Static Server    │
                       │ (Port 9000)      │
                       │                  │
                       └──────────────────┘
```

## 🔧 Prerequisites {#prerequisites}

- 🐳 **Docker**: Version 20.10 or higher
- 📦 **Docker Compose**: Version 2.0 or higher
- 💻 **Operating System**: macOS, Linux, or Windows with WSL2
- 💾 **Git**: For cloning frontend repository
- 🌐 **curl**: For testing API endpoints

### 🍎 Installation on macOS

```bash
# Install Docker Desktop
brew install --cask docker

# Verify installation
docker --version
docker-compose --version
```

## 📂 Tasks Overview {#tasks-overview}

| Task | Description | Key Components |
|------|-------------|----------------|
| **📦 Task 0** | Basic Ubuntu container with Hello World | Docker basics, Ubuntu base image |
| **🐍 Task 1** | Flask backend API development | Python3, Flask, REST API |
| **🌐 Task 2** | Frontend integration with Nginx | Static file serving, Nginx configuration |
| **⚡ Task 3** | Dynamic content with AJAX | JavaScript, CORS, API integration |
| **📦 Task 4** | Docker Compose orchestration | Multi-container coordination |
| **🔄 Task 5** | Reverse proxy implementation | Load balancing, routing |
| **📈 Task 6** | Horizontal scaling | Multiple backend instances |

## 🚀 Quick Start {#quick-start}

### 📈 Running the Latest Version (Task 6 - Horizontal Scaling)

```bash
# Clone and navigate to the project
cd /path/to/Docker_PROJECT

# Navigate to Task 6
cd task6

# Start the application with 2 backend servers
docker-compose up --scale back-end=2

# Or run in detached mode
docker-compose up --scale back-end=2 -d

# Test the API
curl http://localhost/api/hello

# Test the frontend
open http://localhost

# Clean up
docker-compose down
```

### 🔄 Running Other Tasks

```bash
# Task 0 - Basic Hello World
cd task0
docker build -t softy-pinko:task0 .
docker run softy-pinko:task0

# Task 1 - Flask Backend
cd task1
docker build -t softy-pinko:task1 .
docker run -p 5252:5252 softy-pinko:task1

# Task 4 - Docker Compose
cd task4
docker-compose up
```

## 📝 Detailed Task Descriptions {#detailed-task-descriptions}

### 📦 Task 0: Basic Docker Container
**🎯 Objective**: Create a basic Ubuntu container that prints "Hello, World!"

**📁 Key Files**:
- `task0/Dockerfile`

**⚙️ Commands**:
```bash
cd task0
docker build -t softy-pinko:task0 .
docker run softy-pinko:task0
```

**🎓 Learning Outcomes**:
- 🐳 Docker basics
- 📝 Dockerfile syntax
- 🏗️ Container building and running

### 🐍 Task 1: Backend Development
**🎯 Objective**: Add Python Flask backend with REST API endpoint

**📁 Key Files**:
- `task1/Dockerfile` - Extended with Python3, pip3, Flask
- `task1/api.py` - Flask application with `/api/hello` endpoint

**🔗 API Endpoint**:
- `GET /api/hello` → Returns "Hello, World!"

**⚙️ Commands**:
```bash
cd task1
docker build -t softy-pinko:task1 .
docker run -p 5252:5252 softy-pinko:task1
curl http://localhost:5252/api/hello
```

**🎓 Learning Outcomes**:
- 🐍 Python in Docker
- 🌶️ Flask web framework
- 🔗 REST API development
- 🔌 Container port mapping

### 🌐 Task 2: Frontend Integration
**🎯 Objective**: Separate backend and frontend, add Nginx static file server

**📁 Key Files**:
- `task2/back-end/` - Flask backend moved to separate directory
- `task2/front-end/Dockerfile` - Nginx-based frontend container
- `task2/front-end/softy-pinko-front-end.conf` - Nginx configuration
- `task2/front-end/softy-pinko-front-end/` - Cloned frontend repository

**⚙️ Commands**:
```bash
cd task2
# Build and run backend
docker build -t softy-pinko-back-end:task2 ./back-end
docker run -p 5252:5252 softy-pinko-back-end:task2

# In another terminal, build and run frontend
docker build -t softy-pinko-front-end:task2 ./front-end
docker run -p 9000:9000 softy-pinko-front-end:task2
```

**🎓 Learning Outcomes**:
- 🔀 Microservices separation
- ⚙️ Nginx configuration
- 📁 Static file serving
- 🏗️ Multi-container architecture

### ⚡ Task 3: Dynamic Content
**🎯 Objective**: Add AJAX functionality and CORS support for dynamic content

**⭐ Key Features**:
- 📝 Updated `index.html` with dynamic content div
- 📱 JavaScript AJAX calls to backend API
- 🔄 CORS enabled on Flask backend
- ⚡ Dynamic content updates on page load

**📁 Key Files**:
- `task3/back-end/api.py` - Added CORS support
- `task3/back-end/Dockerfile` - Installs flask-cors
- `task3/front-end/softy-pinko-front-end/index.html` - Added JavaScript

**🎓 Learning Outcomes**:
- 🔄 Cross-Origin Resource Sharing (CORS)
- 📱 AJAX and JavaScript integration
- ⚡ Dynamic web content
- 🔗 Frontend-backend communication

### 📦 Task 4: Docker Compose
**🎯 Objective**: Orchestrate multiple containers using Docker Compose

**📁 Key Files**:
- `task4/docker-compose.yml` - Multi-service orchestration

**🚀 Services**:
- `back-end`: Flask API server
- `front-end`: Nginx static server

**⚙️ Commands**:
```bash
cd task4
docker-compose up
docker-compose up -d  # Detached mode
docker-compose down   # Stop and remove containers
```

**🎓 Learning Outcomes**:
- 🎼 Docker Compose orchestration
- 🔗 Service dependencies
- 🌐 Network communication between containers
- 🔄 Container lifecycle management

### 🔄 Task 5: Reverse Proxy
**🎯 Objective**: Add Nginx reverse proxy for unified access point

**📁 Key Files**:
- `task5/proxy/Dockerfile` - Proxy server container
- `task5/proxy/proxy.conf` - Nginx proxy configuration

**🏗️ Architecture**:
- 🚪 Single entry point on port 80
- 🔗 Routes `/api/*` to backend
- 🌐 Routes `/` to frontend
- ⚙️ Load balancing preparation

**🎓 Learning Outcomes**:
- 🔄 Reverse proxy concepts
- ⚙️ Nginx proxy configuration
- 🗺️ Request routing
- 🚪 Single point of access

### 📈 Task 6: Horizontal Scaling
**🎯 Objective**: Implement horizontal scaling with multiple backend instances

**⭐ Key Features**:
- 📈 Multiple backend instances
- 🔄 Round-robin load balancing
- 🔍 Automatic service discovery
- 🏗️ Scalable architecture

**📁 Key Files**:
- `task6/2-api-servers.txt` - Contains scaling command
- `task6/docker-compose.yml` - Updated for scaling
- `task6/proxy/proxy.conf` - Load balancing configuration

**⚙️ Commands**:
```bash
cd task6
docker-compose up --scale back-end=2    # 2 backend instances
docker-compose up --scale back-end=5    # 5 backend instances
```

**🎓 Learning Outcomes**:
- 📈 Horizontal scaling concepts
- ⚖️ Load balancing algorithms
- 🔍 Service discovery
- 🚀 High availability architecture

## 💡 Usage Examples {#usage-examples}

### ⚖️ Testing Load Balancing

```bash
# Start with multiple backend instances
cd task6
docker-compose up --scale back-end=3 -d

# Test load balancing with multiple requests
for i in {1..10}; do 
    curl http://localhost/api/hello
    echo " - Request $i"
    sleep 1
done

# Check logs to see requests distributed across backends
docker logs task6-back-end-1 | grep "GET /api/hello"
docker logs task6-back-end-2 | grep "GET /api/hello"
docker logs task6-back-end-3 | grep "GET /api/hello"
```

### 💻 Development Workflow

```bash
# Start development environment
cd task6
docker-compose up --scale back-end=2

# Make changes to backend code
# Rebuild and restart
docker-compose build back-end
docker-compose up --scale back-end=2 --force-recreate
```

### 🚀 Production Deployment

```bash
# Production deployment with multiple instances
cd task6
docker-compose up --scale back-end=5 -d

# Monitor container health
docker-compose ps
docker stats

# Scale up/down as needed
docker-compose up --scale back-end=10 -d
```

## 🧪 Testing {#testing}

### 🔗 API Testing
```bash
# Test backend API directly
curl http://localhost:5252/api/hello

# Test through proxy
curl http://localhost/api/hello

# Test with verbose output
curl -v http://localhost/api/hello
```

### 🌐 Frontend Testing
```bash
# Test frontend directly
curl http://localhost:9000

# Test through proxy
curl http://localhost/

# Check dynamic content loading
open http://localhost/
```

### 💪 Load Testing
```bash
# Simple load test
ab -n 1000 -c 10 http://localhost/api/hello

# Or using curl in a loop
for i in {1..100}; do curl http://localhost/api/hello & done
```

## 🔧 Troubleshooting {#troubleshooting}

### ⚠️ Common Issues

**🚫 Port Already in Use**
```bash
# Check what's using the port
lsof -i :80
lsof -i :5252

# Kill processes using the ports
sudo kill -9 <PID>
```

**🚨 Container Won't Start**
```bash
# Check container logs
docker-compose logs <service-name>
docker logs <container-name>

# Check container status
docker-compose ps
docker ps -a
```

**🚫 CORS Issues**
```bash
# Verify CORS is enabled in backend
curl -H "Origin: http://localhost:9000" \
     -H "Access-Control-Request-Method: GET" \
     -X OPTIONS \
     http://localhost/api/hello
```

**⚖️ Load Balancing Not Working**
```bash
# Check nginx configuration
docker exec task6-proxy-1 cat /etc/nginx/conf.d/default.conf

# Verify backend containers are running
docker-compose ps back-end
```

### 🔍 Debugging Commands

```bash
# Enter container shell
docker exec -it <container-name> /bin/bash

# Check network connectivity
docker network ls
docker network inspect task6_default

# View real-time logs
docker-compose logs -f

# Check resource usage
docker stats
```

### 🧼 Clean Up Commands

```bash
# Stop and remove containers
docker-compose down

# Remove volumes
docker-compose down -v

# Remove images
docker rmi $(docker images -q)

# Complete cleanup
docker system prune -a
```

## 🌐 Network Architecture {#network-architecture}

### 📱 Container Communication
- 🌐 All containers communicate through Docker's internal network
- 🏷️ Service names are used for inter-container communication
- 🔄 Nginx proxy routes external traffic to appropriate services

### 🔌 Port Mapping
- **Port 80**: Nginx proxy (main entry point)
- **Port 9000**: Frontend development access
- **Port 5252**: Backend development access (when not behind proxy)

### 🌐 DNS Resolution
```bash
# Inside containers, services resolve to:
back-end     -> 172.18.0.2, 172.18.0.3, ... (scaled instances)
front-end    -> 172.18.0.4
proxy        -> 172.18.0.5
```

## 📊 Performance Considerations {#performance-considerations}

### 📈 Scaling Guidelines
- **💻 2-3 backends**: Good for development
- **🏗️ 5-10 backends**: Suitable for moderate load
- **🚀 10+ backends**: High-traffic scenarios

### 📊 Resource Monitoring
```bash
# Monitor resource usage
docker stats

# Check container health
docker-compose ps
```

## 🔐 Security Considerations {#security-considerations}

- 👥 Containers run with non-root users where possible
- 🔌 Only necessary ports are exposed
- 🛡️ Nginx proxy provides additional security layer
- 🔄 CORS is properly configured

## 📈 Future Enhancements {#future-enhancements}

- [ ] 🗄️ Add database integration
- [ ] 🔒 Implement authentication
- [ ] 🔒 Add SSL/TLS support
- [ ] ❤️ Container health checks
- [ ] 📊 Monitoring and logging
- [ ] 🚀 CI/CD pipeline integration
- [ ] ☁️ Kubernetes deployment
- [ ] 🏗️ Production-ready configurations

## 🤝 Contributing {#contributing}

1. 🍴 Fork the repository
2. 🌱 Create a feature branch
3. ✨ Make your changes
4. 🧪 Test thoroughly
5. 📤 Submit a pull request

## 📄 License {#license}

This project is part of the HBNB Library educational curriculum.

---

**📁 Project Structure Summary:**
```
Docker_PROJECT/
├── README.md                 # This comprehensive guide
├── task0/                   # Basic Ubuntu container
├── task1/                   # Flask backend development
├── task2/                   # Frontend integration
├── task3/                   # Dynamic content with AJAX
├── task4/                   # Docker Compose orchestration
├── task5/                   # Reverse proxy implementation
└── task6/                   # Horizontal scaling
    ├── 2-api-servers.txt    # Scaling command
    ├── docker-compose.yml   # Multi-service orchestration
    ├── back-end/           # Flask API backend
    ├── front-end/          # Nginx static frontend
    └── proxy/              # Nginx reverse proxy
```

**⚡ Quick Commands Reference:**
```bash
# Latest version with scaling
cd task6 && docker-compose up --scale back-end=2

# Test API
curl http://localhost/api/hello

# View logs
docker-compose logs -f

# Clean up
docker-compose down
```

For detailed task-specific instructions, navigate to the respective task directory and refer to the individual components.
