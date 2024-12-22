# Softy Pinko Docker Project

This project demonstrates containerization of a web application using Docker, featuring a front-end server, multiple back-end instances, and a reverse proxy with load balancing capabilities.

## Project Structure

```bash
.
├── task0/  # Basic Docker image
├── task1/  # Flask backend setup
├── task2/  # Frontend with Nginx
├── task3/  # Connected frontend and backend
├── task4/  # Docker Compose implementation
├── task5/  # Reverse proxy setup
└── task6/  # Horizontal scaling
```

## Tasks Overview

### Task 0: First Docker Image

- Basic Ubuntu-based Docker image
- Updates system packages
- Outputs "Hello, World!"

### Task 1: Backend

- Flask server implementation
- Runs on port 5252
- Simple API endpoint `/api/hello`
- Python and Flask setup in Docker

### Task 2: Frontend

- Nginx server serving static content
- Hosts Softy Pinko frontend template
- Runs on port 9000
- Custom Nginx configuration

### Task 3: Frontend-Backend Connection

- CORS implementation for API access
- Dynamic content loading from backend
- jQuery AJAX requests
- Connected architecture

### Task 4: Docker Compose Integration

- Multi-container orchestration
- Service dependency management
- Single command deployment
- Simplified configuration

### Task 5: Reverse Proxy

- Nginx reverse proxy implementation
- Single entry point on port 80
- Traffic routing to frontend/backend
- Improved security architecture

### Task 6: Horizontal Scaling

- Multiple backend instances
- Round-robin load balancing
- Scalable architecture
- High availability setup

## Requirements

- Docker
- Docker Compose
- Git (for frontend template)

## Installation & Setup

1. Clone the repository:

```bash
git clone [your-repository-url]
```

2. Navigate to desired task directory:

```bash
cd taskX
```

3. Build and run containers:

```bash
# For tasks 0-3
docker build -t softy-pinko:taskX .
docker run -it softy-pinko:taskX

# For tasks 4-6
docker-compose up --build
```

## Testing

### Task 0

```bash
docker run softy-pinko:task0
# Should output: Hello, World!
```

### Tasks 1-3

- Backend: <http://localhost:5252/api/hello>
- Frontend: <http://localhost:9000>

### Tasks 4-6

- Access via: <http://localhost>
- API endpoints available through proxy
- Static content served through proxy

## Load Balancing (Task 6)

To run with multiple backend instances:

```bash
docker-compose up --scale back-end=2
```

## Architecture

```bash
Client -> Nginx Proxy (80) -> Frontend (9000)
                          -> Backend1 (5252)
                          -> Backend2 (5252)
```

## Additional Notes

- Frontend template source: <https://github.com/atlas-school/softy-pinko-front-end>
- Port mappings can be modified in docker-compose.yml
- Nginx configurations can be customized in conf files
- CORS is enabled for development purposes
