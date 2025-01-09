# Task
# User Authentication APIs

This project implements basic user authentication APIs using **Node.js**, **Express**, **MongoDB**, and various libraries such as **bcrypt**, **jwt**, **nodemailer**, **joi**, and **mongoose**.

## Features

1. **User Registration**
   - Endpoint for user registration with email, password, and username.
   - Passwords are hashed using **bcrypt**.
   - Input validation is implemented with **joi**.

2. **User Login**
   - Endpoint for user login using username and password.
   - Returns a JWT token upon successful login.

3. **Forgot Password**
   - Endpoint for requesting a password reset.
   - Sends a reset link to the user's email using **nodemailer**.
   - Allows users to set a new password via the reset link.

## Technologies Used

- **Node.js**: JavaScript runtime for building scalable applications.
- **Express.js**: Web framework for creating RESTful APIs.
- **MongoDB**: NoSQL database for storing user data.
- **Mongoose**: ODM library for MongoDB.
- **bcrypt**: Library for hashing passwords.
- **jsonwebtoken (JWT)**: Library for creating secure tokens.
- **nodemailer**: Library for sending emails.
- **joi**: Library for input validation.

## Installation

1. Clone the repository:

   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory and add the following configuration:

   ```env
   PORT=3000
   MONGO_URI=<your_mongodb_connection_string>
   JWT_SECRET=<your_jwt_secret>
   EMAIL_USER=<your_email>
   EMAIL_PASS=<your_email_password>
   ```

4. Start the server:

   ```bash
   npm start
   ```

   The server will run on `http://localhost:3000` by default.

## API Endpoints

### 1. User Registration

**POST** `/api/register`

- **Request Body**:

  ```json
  {
    "username": "exampleUser",
    "email": "user@example.com",
    "password": "password123"
  }
  ```

- **Response**:

  ```json
  {
    "message": "User registered successfully."
  }
  ```

### 2. User Login

**POST** `/api/login`

- **Request Body**:

  ```json
  {
    "username": "exampleUser",
    "password": "password123"
  }
  ```

- **Response**:

  ```json
  {
    "token": "<jwt_token>"
  }
  ```

### 3. Forgot Password

**POST** `/api/forgot-password`

- **Request Body**:

  ```json
  {
    "email": "user@example.com"
  }
  ```

- **Response**:

  ```json
  {
    "message": "Password reset link sent to your email."
  }
  ```

### 4. Reset Password

**POST** `/api/reset-password`

- **Request Body**:

  ```json
  {
    "token": "<reset_token>",
    "newPassword": "newPassword123"
  }
  ```

- **Response**:

  ```json
  {
    "message": "Password updated successfully."
  }
  ```

## Folder Structure

```
.
├── controllers
│   ├── authController.js
├── models
│   ├── User.js
├── routes
│   ├── authRoutes.js
├── utils
│   ├── email.js
├── middlewares
│   ├── authMiddleware.js
├── app.js
├── server.js
├── .env
├── package.json
```

## Libraries and Packages

- **bcrypt**: For hashing passwords.
- **jsonwebtoken**: For generating and verifying JWT tokens.
- **mongoose**: For database modeling and interaction with MongoDB.
- **nodemailer**: For sending password reset emails.
- **joi**: For validating user inputs.

## Submission Guidelines

- Ensure the code is properly formatted and documented.
- Include appropriate error handling for all APIs.
- Add test cases to validate API functionality (if possible).

---

### Happy Coding! 🚀
