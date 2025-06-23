Create or update the README.md in your root folder with the following:

md
Copy
Edit
# DevOps Intern Assignment – Docker + NGINX + Compose

## 🛠 Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/krishnarohit1/devops-nginx-docker.git
   cd devops-nginx-docker
Run the system:

bash
Copy
Edit
docker-compose up --build
Open in your browser:

Go Service:

http://localhost:8080/service1/ping

http://localhost:8080/service1/hello

Python Service:

http://localhost:8080/service2/ping

http://localhost:8080/service2/hello

🔁 How Routing Works
This setup uses NGINX as a reverse proxy:

Requests to /service1 are routed to the Go application (running in its own container on port 8001)

Requests to /service2 are routed to the Python Flask application (on port 8002)

Everything is accessible through a single port: localhost:8080

Routing logic is defined in nginx/nginx.conf:

nginx
Copy
Edit
location /service1/ {
    proxy_pass http://service_1:8001/;
}

location /service2/ {
    proxy_pass http://service_2:8002/;
}
🎁 Bonus Features
✅ Clean Docker and Docker Compose setup

✅ NGINX logging enabled for all incoming requests

✅ Modular folder structure

✅ [Optional if implemented] Healthchecks (can be added in docker-compose.yml)

📝 All services run with one command: docker-compose up --build


![devops](https://github.com/user-attachments/assets/ce77de70-e3ac-4d1e-a33b-c3ad4b49d50b)
