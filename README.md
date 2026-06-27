# JWT Authentication API

A simple authentication backend built using Node.js, Express.js, MongoDB, bcrypt, and JWT.

## Features

* User Signup
* User Login
* Secure Password Hashing using bcrypt
* JWT Token Generation
* Protected Routes
* Token Expiry Handling
* Invalid Credential Handling

## Tech Stack

* Node.js
* Express.js
* MongoDB
* bcrypt
* jsonwebtoken
* dotenv

## Project Structure

```text
task_2/
│
├── config/
│   └── db.js
├── controllers/
│   └── authController.js
├── middleware/
│   └── authMiddleware.js
├── models/
│   └── User.js
├── routes/
│   └── authRoutes.js
├── .env.example
├── .gitignore
├── README.md
└── server.js
```

## Installation

Install dependencies:

```bash
npm install
```

## Run Project

```bash
node server.js
```

Or using nodemon:

```bash
npx nodemon server.js
```

## Environment Variables

Create `.env` file:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/authdb
JWT_SECRET=your_secret_key
```

## API Endpoints

### Signup

**POST** `/api/auth/signup`

Request Body:

```json
{
  "username": "navaneeth",
  "email": "nav@gmail.com",
  "password": "123456"
}
```

Response:

```json
{
  "message": "User registered successfully"
}
```

---

### Login

**POST** `/api/auth/login`

Request Body:

```json
{
  "email": "nav@gmail.com",
  "password": "123456"
}
```

Response:

```json
{
  "message": "Login successful",
  "token": "JWT_TOKEN"
}
```

---

### Protected Route

**GET** `/api/auth/profile`

Header:

```text
Authorization: Bearer JWT_TOKEN
```

Response:

```json
{
  "message": "Protected route accessed"
}
```

## Author

Navaneeth Kiran
