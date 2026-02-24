# 📌 E-Todo – Collaborative Task Management API

## 📖 Overview

E-Todo is a collaborative task management API built with **Node.js, Express and MySQL**.
It allows users to manage projects, tasks (todos), and project members with role-based permissions.

The system implements secure authentication using **JWT (JSON Web Token)** and enforces strict access control based on user roles.

---

## 🚀 Features

### 🔐 Authentication

* JWT-based authentication
* Protected routes via middleware
* Role-based authorization (admin / manager / member)

### 👤 User

* Get current authenticated user
* Get todos assigned to the user

### ✅ Todos

* Create a task
* Update a task
* Delete a task
* Retrieve tasks
* Assign users to tasks
* Role-based access control

### 👥 Project Members

* List project members
* Add new member (admin/manager only)
* Update member role
* Remove member (with permission rules)

---

## 🛠 Tech Stack

* **Node.js**
* **Express**
* **MySQL**
* **Docker & Docker Compose**
* **JWT Authentication**
* **Postman (API testing)**

---

## ⚙️ Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/e-todo.git
cd e-todo
```

### 2️⃣ Start Docker

```bash
docker compose up --build
```

The API will run on:

```
http://localhost:3000
```

---

## 🗄 Database

MySQL is used as the database.

Main tables:

* `user`
* `projects`
* `project_members`
* `todo`
* `todo_assignments`

To access MySQL inside Docker:

```bash
sudo docker exec -it <container-name> mysql -u root -p
```

---

## 🔑 Authentication

All protected routes require:

```
Authorization: Bearer <your_token>
```

Token is generated during login.

---

## 📡 API Endpoints

### 👤 User

| Method | Endpoint          | Description             |
| ------ | ----------------- | ----------------------- |
| GET    | `/api/user`       | Get authenticated user  |
| GET    | `/api/user/todos` | Get user assigned todos |

---

### ✅ Todos

| Method | Endpoint         | Description              |
| ------ | ---------------- | ------------------------ |
| GET    | `/api/todos`     | Get all accessible todos |
| POST   | `/api/todos`     | Create new todo          |
| PUT    | `/api/todos/:id` | Update todo              |
| DELETE | `/api/todos/:id` | Delete todo              |

---

### 👥 Project Members

| Method | Endpoint                          | Description          |
| ------ | --------------------------------- | -------------------- |
| GET    | `/api/projects/1/members`         | List project members |
| POST   | `/api/projects/1/members`         | Add member           |
| PUT    | `/api/projects/1/members/:userId` | Update role          |
| DELETE | `/api/projects/1/members/:userId` | Remove member        |

---

## 🔐 Roles & Permissions

| Role    | Permissions                        |
| ------- | ---------------------------------- |
| Admin   | Full access to project and members |
| Manager | Can manage members (not admins)    |
| Member  | Limited access to assigned tasks   |

Permission checks are enforced in backend routes before database operations.

---

## 🧪 Testing

API was tested using **Postman**.

---

## ✅ Quality Practices

* Role-based access control
* Error handling with proper HTTP status codes
* Structured route separation
* SQL parameterization to prevent injection
* Iterative testing and debugging

---

## 📚 Lessons Learned

* Importance of strict permission logic
* Handling datetime formats correctly for MySQL
* Debugging using logs and structured testing
* Working collaboratively in a backend project

---

## 👥 Team

* Britney WANKPO-SONON – Backend / API / Database / Authentication / Frontend
* Léo BOUANA - Backend / Frontend
* Alicia ANDRIANARIVELO - Docker / Frontend

---

## 📌 Future Improvements

* Input validation middleware
* Automated tests
* API documentation (Swagger)
* Improved error messages
* UI/UI

---

