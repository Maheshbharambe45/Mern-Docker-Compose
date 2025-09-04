🚀 MERN Docker Compose
A simple MERN (MongoDB, Express, React, Node.js) stack application using Docker and Docker Compose.

🐳 Run with Docker Compose (Recommended)
Start all services (frontend, backend, and MongoDB) with a single command:

docker compose up -d

Once started:

🖥️ Frontend: http://localhost:5173

⚙️ Backend: http://localhost:5050

🗄️ MongoDB: Accessible at localhost:27017

🛑 To stop and remove everything:
docker compose down --volumes

This removes containers, networks, and volumes created by Compose.

⚙️ Manual Setup (Optional)
If you prefer to build and run containers individually:

Create Docker Network

docker network create mern

Frontend

cd mern/frontend
docker build -t mern-frontend .
docker run --name=frontend --network=mern -d -p 5173:5173 mern-frontend

MongoDB

docker run --network=mern --name mongodb -d -p 27017:27017 -v mongo:/data/db mongo:latest

Backend

cd mern/backend
docker build -t mern-backend .
docker run --name=backend --network=mern -d -p 5050:5050 mern-backend

📁 Project Structure
.
├── docker-compose.yml
├── mern
│   ├── backend
│   └── frontend
└── README.md

🧰 Tech Stack
MongoDB – NoSQL database

Express.js – Backend web framework

React.js – Frontend UI library

Node.js – JavaScript runtime

Docker & Docker Compose – Containerization and orchestration
