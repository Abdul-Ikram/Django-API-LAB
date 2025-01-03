# User Authentication API

This API module handles user registration, authentication, email verification, password reset, and user management in a Django project.

## Features

-   User Registration with email verification
-   JWT-based authentication
-   OTP regeneration for email verification
-   Login functionality with token generation
-   Password reset (request and confirm)
-   Delete all users (Admin utility)

## Endpoints

### Base URL

All endpoints are prefixed with:  
`/userflow/api/`

### 1. **Register User**

**POST** `/register/`  
Registers a new user and sends an OTP for email verification.

**Request Body:**

```json
{
  "email": "user@example.com",
  "password": "password123",
  "username": "user"
}

```

**Response:**

```json
{
  "status_code": 200,
  "message": "Registration successful. Please check your email to verify your account.",
  "user": {
    "email": "user@example.com",
    "username": "user",
    "is_verified": false
  }
}

```

----------

### 2. **Verify Email**

**POST** `/verify-email/`  
Verifies a user's email with the provided OTP.

**Request Body:**

```json
{
  "email": "user@example.com",
  "otp": "123456"
}

```

**Response:**

```json
{
  "status_code": 200,
  "message": "Your email has been successfully verified."
}

```

----------

### 3. **Regenerate OTP**

**POST** `/regenerate-otp/`  
Generates a new OTP for email verification.

**Request Body:**

```json
{
  "email": "user@example.com"
}

```

**Response:**

```json
{
  "status_code": 200,
  "message": "A new OTP has been successfully generated and sent to your email address."
}

```

----------

### 4. **Login**

**POST** `/login/`  
Authenticates a user and returns JWT tokens upon successful login.

**Request Body:**

```json
{
  "email": "user@example.com",
  "password": "password123"
}

```

**Response:**

```json
{
  "status_code": 200,
  "message": "Login successful. Welcome back!",
  "refresh": "<refresh_token>",
  "access": "<access_token>",
  "data": {
    "user": {
      "id": 1,
      "username": "user",
      "email": "user@example.com",
      "is_verified": true,
      ...
    }
  }
}

```

----------

### 5. **Request Password Reset**

**POST** `/password-reset-request/`  
Sends an OTP to the user's email for password reset.

**Request Body:**

```json
{
  "email": "user@example.com"
}

```

**Response:**

```json
{
  "status_code": 200,
  "message": "Password reset OTP has been sent to your email address."
}

```

----------

### 6. **Confirm Password Reset**

**POST** `/password-reset-confirm/`  
Resets the user's password using the OTP.

**Request Body:**

```json
{
  "email": "user@example.com",
  "otp": "123456",
  "new_password": "newpassword123"
}

```

**Response:**

```json
{
  "status_code": 200,
  "message": "Password updated successfully."
}

```

----------

### 7. **Refresh Token**

**POST** `/token/refresh/`  
Refreshes the access token using a refresh token.

**Request Body:**

```json
{
  "refresh": "<refresh_token>"
}

```

**Response:**

```json
{
  "access": "<new_access_token>"
}

```

----------

### 8. **Delete All Users**

**DELETE** `/delete-all-users/`  
Deletes all users from the database. **(Admin utility)**

**Response:**

```json
{
  "status_code": 200,
  "message": "All users deleted successfully."
}

```
----------
    
**Access the API** Navigate to `http://127.0.0.1:8000/userflow/api/`.

----------

## Technologies Used

-   **Django**: Backend framework
-   **Django REST Framework**: API development
-   **Django Simple JWT**: Token-based authentication
-   **SQLite**: Default database (can be easily switched)

----------

## Contributing

Feel free to fork this repository, create a feature branch, and submit a pull request. Contributions are welcome!

----------
