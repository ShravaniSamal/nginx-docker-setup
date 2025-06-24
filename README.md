📦 **Project Overview
This project sets up a reverse proxy using Nginx and Docker Compose to route HTTP requests to two backend services**:

✅ **Service 1**: Golang app running on port 8001

✅ **Service 2**: Python Flask app running on port 8002, managed with uv

Everything is containerized and served on http://65.0.99.243:8080 using path-based routing via Nginx.

🛠 **Setup Instructions**
1. **Clone the repository**:

git clone https://github.com/ShravaniSamal/nginx-docker-setup.git
cd nginx-docker-setup
2. Start all services with Docker Compose:

sudo docker-compose up --build -d
3. Access the services in your browser:

http://65.0.99.243:8080/service1/ping

http://65.0.99.243:8080/service1/hello

http://65.0.99.243:8080/service2/ping

http://65.0.99.243:8080/service2/hello

📁 **Folder Structure**

nginx-docker-setup/
├── docker-compose.yml
├── nginx/
│   ├── nginx.conf          # Nginx routing and logging config
│   └── Dockerfile          # Nginx container setup
├── service_1/
│   ├── main.go             # Golang app source
│   └── Dockerfile          # Dockerfile for Go app
├── service_2/
│   ├── app.py              # Flask app source
│   ├── pyproject.toml      # uv dependency file
│   └── Dockerfile          # Dockerfile for Python uv service
└── README.md

🔁**How Routing Works** (Nginx Reverse Proxy)
Nginx listens on **port 8080**

**Routes /service1/*** → Go service running on service1:8001

**Routes /service2/*** → Python Flask service running on service2:8002

All routing is defined in **nginx/nginx.conf**

💡 **Bonus Features Implemented**

✅ **Docker health** checks for both services

✅ Nginx logging for all requests

✅ Modular and clean Dockerfile structure

✅ Tested and deployed on **AWS EC2 Ubuntu instance**

✅ Final system can be launched with a single command:

sudo docker-compose up --build -d
