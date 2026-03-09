# 🎯 MicroGoals - Secure Goal Management Backend API

A secure RESTful backend API built with **Node.js**, **Express.js**, and **MongoDB Atlas**.  
Users can register, login, and manage their personal goals through protected CRUD operations.

---

## 🚀 Features

- ✅ User Registration & Login
- ✅ JWT-based Authentication
- ✅ Password Hashing with bcrypt
- ✅ Create, Read, Update & Delete Goals
- ✅ Protected Routes (JWT Middleware)
- ✅ Centralized Error Handling
- ✅ MongoDB Atlas Cloud Database

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Node.js | JavaScript Runtime |
| Express.js | Web Framework |
| MongoDB Atlas | Cloud Database |
| Mongoose | MongoDB ODM |
| JWT | Authentication Tokens |
| bcryptjs | Password Hashing |
| dotenv | Environment Variables |

---

## 📁 Folder Structure

```
Backend/
├── Middlewares/
│   ├── authMiddleware.js   ← Verifies JWT token
│   └── errormiddleware.js  ← Centralized error handler
├── Model/
│   ├── UserModel.js        ← User schema
│   └── GoalModel.js        ← Goal schema
├── Router/
│   ├── AuthRouter.js       ← Register & Login routes
│   └── GoalRouter.js       ← CRUD goal routes
├── utills/
│   └── genratetoken.js     ← JWT token generator
├── validation/
│   └── userValidation.js   ← Input validation
├── .gitignore
├── Index.js                ← Main server entry point
└── package.json
```

---

## ⚙️ Setup & Installation

### 1. Clone the repository
git clone https://github.com/SRISARATHATEJASWI16/Microgoal_NM_Backend_Sem4.git
cd Backend

### 2. Install dependencies
```bash
npm install
```

### 3. Create `.env` file
```env
PORT=5000
MONGO_URL=your_mongodb_atlas_connection_string
SECRET_KEY=your_secret_key
```

### 4. Run the server
```bash
node Index.js
```

You should see:
```
MongoDB Connected
Server running on port 5000
```

---

## 📡 API Endpoints

### Auth Routes
| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| POST | `/signup` | Register new user | No |
| POST | `/login` | Login and get JWT token | No |

### Goal Routes
| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| POST | `/create` | Create a new goal | Yes |
| GET | `/:id` | Get a goal by ID | Yes |
| PUT | `/:id` | Update goal (mark completed) | Yes |
| DELETE | `/:id` | Delete a goal | Yes |

---

## 🔐 Authentication

All goal routes are protected. You must send the JWT token in the request header:

```
Authorization: Bearer <your_token>
```

---

## 📸 API Testing

APIs were tested using **Thunder Client** (VS Code Extension).

### Register a User
```json
POST /signup
{
  "name": "Teju",
  "email": "teju@test.com",
  "password": "password123"
}
```

### Login
```json
POST /login
{
  "email": "teju@test.com",
  "password": "password123"
}
```

### Create a Goal (with token)
```json
POST /create
Headers: Authorization: Bearer <token>
{
  "title": "Learn Node.js"
}
```

---

## 👤 Author

**Sai Saratha Tejaswi**  
B.Sc Computer Science  

---

## 📄 License

This project is for educational purposes.
