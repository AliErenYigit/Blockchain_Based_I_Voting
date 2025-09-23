# Blockchain_Based_I_Voting

# 🗳️ Blockchain-Based I-Vote Application

This project is a microservice-based electronic voting system. It allows conducting elections both with database-backed and blockchain-based storage.
The mobile side is developed with React Native (Expo), while the backend is built with a Node.js microservice architecture.

# 🚀 Features

* User registration and authentication (JWT & Email verification)

* Create and manage elections (with start & end dates)

* Add and visualize candidates/options (Image Service – AWS S3)

* Voting (can be stored both in the database and on the blockchain)

* Dynamic calculation of results

* Address and user group management

* Centralized access to all services through the Gateway

# 📂 Architecture & Microservices

The project runs on Docker Compose, and each service is independent:

Service | Port | Description

* **gateway** – 3000 – API Gateway (entry point for all requests)

* **auth-service** – 5000 – User authentication (JWT, login)

* **election-service** – 5001 – Election CRUD operations

* **option-service** – 5002 – Candidate/option operations

* **result-service** – 5003 – Election result calculations

* **user-service** – 5004 – User registration and management

* **vote-service** – 5005 – Voting operations

* **mail-service** – 5006 – Email verification & password reset

* **adress-service** – 5007 – Election addresses (city, district, neighborhood management)

* **image-service** – 5008 – Image upload & management (S3 integration)

* ***postgres** – 5432 – Shared database

# 🛠️ Technologies Used

**Backend:** Node.js, Express.js, REST API

**Database:** PostgreSQL, DynamoDB (for some services)

**Blockchain:** Ethereum / Smart Contracts (for voting)

**Frontend:** React Native (Expo)

**Containerization:** Docker, Docker Compose

**Authentication:** JWT, Email Verification

**Storage:** AWS S3 (image-service)

# ⚙️ Setup & Run
<pre> # Clone the repository: git clone https://github.com/EreenKara/Blockchain_Based_I_Voting.git 
  cd Blockchain_Based_I_Voting 
  
  # Run all services with Docker Compose: 
  docker-compose up --build </pre>

Services will be available at the following default addresses:

<pre> API Gateway: http://localhost:3000 
  Auth Service: http://localhost:5000 
  User Service: http://localhost:5004 
  (see the table above for other services) </pre>
# 📱 Mobile Application

Developed with React Native (Expo).
Through the mobile app, users can:

* Log in

* Join elections

* Cast votes

* View results

# 📊 System Flow

User registers → Email verification is performed

Admin creates a new election → Candidates are added

If the user has access, they can vote

Votes are stored both in the database and on the blockchain

The election automatically closes at its end date

Results are calculated by the result-service and published
