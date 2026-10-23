# Authentication API

A personal backend project built with **Node.js, Express.js, and MongoDB** to implement secure user authentication using password hashing and JSON Web Tokens (JWT).

## About the Project

This project implements the core authentication features of a REST API, including user registration, login, password hashing, JWT generation, and protected routes.

**Author:** Chibout Wahb  
**Project Type:** Personal Project  
**Purpose:** Learning and practicing backend development, REST APIs, database integration, and authentication security.

## Features

- User registration and login
- Password hashing with `bcrypt`
- JWT generation and verification
- Protected routes using Bearer tokens
- MongoDB database integration with Mongoose
- Input validation and appropriate HTTP status codes
- Duplicate email prevention
- Environment variable configuration for sensitive information

## Tech Stack

- **Node.js** — JavaScript runtime
- **Express.js** — Web framework
- **MongoDB** — Database
- **Mongoose** — MongoDB object modeling
- **bcrypt** — Password hashing
- **jsonwebtoken** — JWT generation and verification
- **dotenv** — Environment variable management

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Check whether the API is running |
| POST | `/auth/signup` | Register a new user |
| POST | `/auth/login` | Authenticate a user and receive a JWT |
| GET | `/auth/me` | Retrieve the authenticated user's profile |

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/wchibout/auth-api.git
cd auth-api
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the project root, using `.env.example` as a reference.

```env
PORT=3000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_long_random_secret
JWT_EXPIRES_IN=1h
```

Replace the example values with your own configuration. Never commit your real `.env` file or expose your database credentials or JWT secret.

### 4. Run the Server

Development mode:

```bash
npm run dev
```

Production mode:

```bash
npm start
```

The API runs at `http://localhost:3000` by default.

## Example Requests

### Register a User

**POST** `/auth/signup`

```json
{
  "name": "Wahb",
  "email": "wahb.test@example.com",
  "password": "StrongPass123"
}
```

### Log In

**POST** `/auth/login`

```json
{
  "email": "wahb.test@example.com",
  "password": "StrongPass123"
}
```

A successful login returns a JWT. Use this token to access protected endpoints.

### Get the Current User

**GET** `/auth/me`

Include the following HTTP header:

```http
Authorization: Bearer YOUR_JWT_TOKEN
```

## Security Measures

- Passwords are hashed before being stored in the database.
- Passwords are never returned in API responses.
- JWTs are verified before protected routes are accessed.
- Invalid or expired tokens are rejected.
- Duplicate email registrations are prevented.
- Sensitive configuration is stored in environment variables.

## Testing

The endpoints can be tested using Thunder Client, Postman, or another HTTP client.

Test scenarios include successful registration and login, duplicate registration, incorrect passwords, and invalid JWTs.

## What I Learned

Through this project, I practiced building RESTful APIs, connecting an application to MongoDB, securely handling passwords, issuing and verifying JWTs, and protecting routes with authentication middleware.

---

**Developed by Chibout Wahb as a personal project.**

**Repository:** [https://github.com/wchibout/auth-api](https://github.com/wchibout/auth-api)