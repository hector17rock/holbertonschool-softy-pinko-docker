# 🐳 Docker Project - Softy Pinko

A Docker-based web application that demonstrates containerization and microservices architecture. This project uses Flask for the backend API and Nginx for the frontend, with Docker Compose for orchestration.

## 📊 What's Inside

- **Task 0-1**: Basic Docker containers and Flask API
- **Task 2-3**: Frontend integration with Nginx and AJAX  
- **Task 4-5**: Docker Compose and reverse proxy
- **Task 6**: Horizontal scaling with load balancing

## 🚀 Quick Start

**Prerequisites**: Docker and Docker Compose installed

```bash
# Install Docker on macOS
brew install --cask docker
```

### 📝 Tasks

**Task 0**: Basic "Hello World" Docker container  
**Task 1**: Flask API backend  
**Task 2**: Nginx frontend server  
**Task 3**: AJAX integration  
**Task 4**: Docker Compose setup  
**Task 5**: Reverse proxy  
**Task 6**: Load balancing and scaling

### 🚀 Running the Project

```bash
# Run the complete application (Task 6)
cd task6
docker-compose up --scale back-end=2

# Test the API
curl http://localhost/api/hello

# Open frontend in browser
open http://localhost

# Stop containers
docker-compose down
```

### 🔄 Individual Tasks

```bash
# Task 0: Basic container
cd task0
docker build -t softy-pinko:task0 .
docker run softy-pinko:task0

# Task 1: Flask API
cd task1
docker build -t softy-pinko:task1 .
docker run -p 5252:5252 softy-pinko:task1

# Task 4: Docker Compose
cd task4
docker-compose up
```

## 💻 Project Structure

```
holbertonschool-softy-pinko-docker/
├── task0/               # Basic Hello World container
│   └── Dockerfile
├── task1/               # Flask API backend
│   ├── Dockerfile
│   └── api.py
├── task2/               # Separate backend and frontend
│   ├── back-end/
│   └── front-end/
├── task3/               # AJAX integration
│   ├── back-end/
│   └── front-end/
├── task4/               # Docker Compose orchestration
│   └── docker-compose.yml
├── task5/               # Reverse proxy
│   ├── docker-compose.yml
│   └── proxy/
└── task6/               # Horizontal scaling
    ├── docker-compose.yml
    ├── back-end/
    ├── front-end/
    └── proxy/
```

## 🧪 Testing

```bash
# Test the API
curl http://localhost/api/hello

# Test load balancing
for i in {1..5}; do curl http://localhost/api/hello; done

# Check logs
docker-compose logs -f
```

## 🔧 Common Commands

```bash
# Check container status
docker-compose ps

# View logs
docker-compose logs -f

# Stop containers
docker-compose down

# Clean up everything
docker system prune -a
```

## 👤 Author

**Héctor Soto** - [@hector17rock](https://github.com/hector17rock)

---

## 📄 License

This project is part of the Holberton School curriculum.
