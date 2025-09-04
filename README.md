# 🚀 MERN Docker Compose

A simple MERN (MongoDB, Express, React, Node.js) stack application using Docker and Docker Compose.

---

## 🐳 Run with Docker Compose (Recommended)

```bash
docker compose up -d
```

🖥️ **Frontend:** [http://localhost:5173](http://localhost:5173)  

⚙️ **Backend:** [http://localhost:5050](http://localhost:5050)  

🗄️ **MongoDB:** `localhost:27017`  

---

### 🛑 Stop and remove all containers, networks, and volumes:

```bash
docker compose down --volumes
```

---

## ⚙️ Manual Setup (Optional)

### 1. Create Docker Network

```bash
docker network create demo
```

---

### 2. Frontend

```bash
cd mern/frontend
docker build -t mern-frontend .
docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend
```

---

### 3. MongoDB

```bash
docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongo:latest
```

---

### 4. Backend

```bash
cd mern/backend
docker build -t mern-backend .
docker run --name=backend --network=demo -d -p 5050:5050 mern-backend
```

---

## 🧰 Tech Stack

- MongoDB  
- Express.js  
- React.js
- Node.js  
- Docker & Docker Compose
- Node.js  
- Docker & Docker Compose
