# CMPE-272 Assignment 1 – Microservices with Flask

## Overview
This project demonstrates a simple **microservices architecture** using **Python Flask**.  
The system consists of two services:
- **User Service (port 5001)** – manages user data (create, retrieve, delete).
- **Order Service (port 5002)** – manages orders and communicates with the User Service to fetch user details.

Each service is independent, can be started separately, and communicates via HTTP requests.

---

## ⚙️ Working

### User Service
- Runs on **port 5001**.
- Endpoints:
  - `GET /users/<id>` → Retrieve user by ID.
  - `POST /users` → Create a new user.
  - `DELETE /users/<id>` → Delete a user.

### Order Service
- Runs on **port 5002**.
- Endpoints:
  - `GET /orders/<id>` → Retrieve order details (with user info from User Service).
  - `POST /orders` → Create a new order.

### Communication
- When an order is retrieved, the Order Service calls the User Service to fetch the user’s details and includes them in the response.

---

## 🖥️ Screenshots / Test Output

### a) Curl Tests for User and Order Service
Example: Create user, create order, and fetch order.
<img width="1132" height="357" alt="Screenshot 2025-09-09 at 1 24 52 PM" src="https://github.com/user-attachments/assets/34bd872e-ef4e-4c88-a544-314d3c8dbac5" />

### b) Running Both Services Simultaneously
<img width="695" height="267" alt="Screenshot 2025-09-09 at 1 23 16 PM" src="https://github.com/user-attachments/assets/02e375c8-d68c-4446-bad8-229e82b6815d" />
<img width="695" height="267" alt="Screenshot 2025-09-09 at 1 23 16 PM" src="https://github.com/user-attachments/assets/d179fca0-2fc0-41f6-bd1b-d26b917b90c1" />

