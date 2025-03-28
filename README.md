# Collaborative-Development-of-a-Full-Stack-Application
# Voting System Group

## For our tasks:
1. **Jhian Kyle Cinco** - Backend Developer (API)
2. **Kercson Didal**    - Frontend Developer (Angular)
3. **Charles Tampos**   - Tester (API and Frontend testing)
4. **MJ Hermosa**       - Documentation Specialist (README.md)
5. **Kerbi Cabardo**    - DevOps Lead (Repository setup, branch management, CI/CD pipeline if applicable)

## Instructions
Members should send the link of your repository on LMS. I will update this README.md later on...

# Group 2 Full-Stack Application

## Project Description
This project is a collaborative full-stack application developed by Group 2. It features a **Node.js + MySQL backend** and an **Angular 19 frontend**. The application provides functionalities such as user authentication, role-based authorization, profile management, and more. The purpose of this application is to provide a robust platform for managing user accounts and profiles securely.

________________________________________________________________________________

## Setup Instructions

### Prerequisites
- **Node.js** (v16 or later)
- **MySQL** (v8 or later)
- **Angular CLI** (v15 or later)
- **Postman** (for API testing)

### Backend Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/AdeptEagle/Group-2-Fullstack-App.git
   cd Group-2-Fullstack-App
   ```
2. Switch to the backend branch:
   ```bash
   git checkout Cinco_backend_API
   ```
3. Navigate to the backend directory:
   ```bash
   cd backend
   ```
4. Install dependencies:
   ```bash
   npm install
   ```
5. Configure environment variables:
   Create a `.env` file in the `backend` directory and add the following:
   ```
   DB_HOST=your-database-host
   DB_USER=your-database-user
   DB_PASSWORD=your-database-password
   DB_NAME=your-database-name
   SMTP_HOST=your-smtp-host
   SMTP_PORT=your-smtp-port
   SMTP_USER=your-smtp-user
   SMTP_PASSWORD=your-smtp-password
   JWT_SECRET=your-jwt-secret
   ```
6. Run database migrations:
   ```bash
   npm run migrate
   ```
7. Start the server:
   ```bash
   npm start
   ```

### Frontend Setup
1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the Angular development server:
   ```bash
   ng serve
   ```

________________________________________________________________________________

## API Endpoints

### Authentication
- **POST** `/api/auth/register`  
  Registers a new user.  
  **Request:**
  ```json
  {
    "email": "user@example.com",
    "password": "password123"
  }
  ```
  **Response:**
  ```json
  {
    "message": "Registration successful. Please verify your email."
  }
  ```

- **POST** `/api/auth/login`  
  Logs in a user and returns a JWT token.  
  **Request:**
  ```json
  {
    "email": "user@example.com",
    "password": "password123"
  }
  ```
  **Response:**
  ```json
  {
    "token": "jwt-token"
  }
  ```

- **POST** `/api/auth/forgot-password`  
  Sends a password reset email.

- **POST** `/api/auth/reset-password`  
  Resets the user's password.

### User Management
- **GET** `/api/users/profile`  
  Retrieves the user's profile.  
  **Authentication Required:** Yes (JWT token)

- **PUT** `/api/users/profile`  
  Updates the user's profile.

________________________________________________________________________________

## Frontend Features
- **Login and Registration:** Users can register and log in to the application.
- **Email Verification:** Users must verify their email before accessing certain features.
- **Forgot Password:** Users can reset their password via email.
- **Profile Management:** Users can view and update their profile information.

________________________________________________________________________________

## Testing Instructions

### API Testing
1. Use Postman to test the API endpoints.
2. Import the provided Postman collection (`postman_collection.json`) from the repository.
3. Test the following:
   - User registration and login.
   - Forgot password and reset password functionality.
   - Profile retrieval and updates.

### Frontend Testing
1. Enable the fake backend by including `fakeBackendProvider` in `app.module.ts`.
2. Test the application in the browser using the Angular development server.
3. Once the API is ready, connect the frontend to the real API and retest.

________________________________________________________________________________

## Contributors
- **Cinco (Backend Developer):** Responsible for implementing backend API endpoints, authentication, and database configurations.
- **Member 1 (Backend Developer):** Task 1, Task 2
- **Member 2 (Backend Developer):** Task 3, Task 4
- **Member 3 (Frontend Developer):** Task 6, Task 7
- **Member 4 (Frontend Developer):** Task 8, Task 9
- **Member 5 (Tester):** Task 11, Task 12, Task 13
- **Member 6 (Documentation Specialist):** Task 14

________________________________________________________________________________

## Submission
- **GitHub Repository:** [Repository Link](https://github.com/AdeptEagle/Group-2-Fullstack-App.git)
- **Branches:** Ensure all branches are merged into the `main` branch.
- **Pull Requests:** Links to all pull requests are available in the repository.