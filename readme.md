```markdown
# User Authentication and Authorization with Bearer Token

## Description

This project is a Node.js application that demonstrates user authentication and authorization using Bearer tokens. It follows the **MVC (Model-View-Controller)** architecture and uses **Express.js**, **Mongoose**, and **JWT (JSON Web Tokens)**. The application includes:

- User registration and login
- Password hashing for security
- JWT generation and verification
- Middleware for token validation
- API documentation with **Postman**

---

## Features

- **User Registration**: Allows users to register by providing a username, email, and password.
- **User Login**: Authenticates users and generates a JWT for future requests.
- **JWT Verification**: Middleware to validate JWTs and attach user information to the request object.
- **Protected Routes**: Routes that require a valid JWT to access.
- **Error Handling**: Graceful error messages for invalid inputs or unauthorized access.
- **Postman Documentation**: Includes detailed API documentation with sample requests and responses.

---

## Tech Stack

- **Node.js**: Runtime environment
- **Express.js**: Web framework
- **Mongoose**: MongoDB object modeling for Node.js
- **JWT**: Token-based authentication
- **Postman**: API testing and documentation tool
- **Render**: For deployment

---

## Setup and Installation

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory and add the following variables:
   ```
   PORT=<your_port>
   MONGO_URI=<your_mongodb_connection_string>
   JWT_SECRET=<your_secret_key>
   ```

4. Start the server:
   ```bash
   npm start
   ```

---

## API Endpoints

### **User Registration**
![user registered](https://github.com/user-attachments/assets/1c844d05-f65c-49f0-82b3-d152bb911934)
User already exist
![user already exist](https://github.com/user-attachments/assets/6f54ab37-9ca4-45d3-85ea-b7c1620d01f5)

- **URL**: `/api/register`
- **Method**: POST
- **Body**: 
  ```json
  {
    "username": "exampleuser",
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

### **User Login**
![user login](https://github.com/user-attachments/assets/13d22826-0848-4fee-82af-70a3d666ed44)
User not exist
![not exist](https://github.com/user-attachments/assets/c4cbbd8d-4226-44d1-ac50-ca04ded303c4)
Invalid pass
![invalid pass](https://github.com/user-attachments/assets/796ae33f-d88f-4d8f-a0b9-ad8e065309aa)

- **URL**: `/api/login`
- **Method**: POST
- **Body**: 
  ```json
  {
    "email": "user@example.com",
    "password": "password123"
  }
  ```
- **Response**:
  ```json
  {
    "token": "your_jwt_token"
  }
  ```

### **Get User Information**
![data added](https://github.com/user-attachments/assets/2a25a8ac-270f-4057-9a8f-e5d391ef0e78)

- **URL**: `/api/user`
- **Method**: GET
- **Headers**:
  ```
  Authorization: Bearer <your_jwt_token>
  ```
- **Response**:
  ```json
  {
    "username": "exampleuser",
    "email": "user@example.com"
  }
  ```

```
