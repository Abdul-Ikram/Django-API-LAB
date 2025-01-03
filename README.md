# Django API Lab

Welcome to the **Django API Lab** repository! This project demonstrates the implementation of modular APIs using Django REST Framework (DRF). Each API is documented separately to ensure scalability and ease of maintenance.

----------

## Table of Contents

1.  [Project Overview](https://github.com/Abdul-Ikram/Django-API-LAB#project-overview)
2.  [Setup Instructions](https://github.com/Abdul-Ikram/Django-API-LAB.git#setup-instructions)
3.  [Postman Collection](https://github.com/Abdul-Ikram/Django-API-LAB.git#postman-collection)
4.  [Available APIs](https://github.com/Abdul-Ikram/Django-API-LAB.git#available-apis)
5.  [Contributing](#contributing)

----------

## Project Overview

This project contains multiple APIs for common backend functionalities. Each API is modular and well-documented, allowing you to easily extend the project.

Current modules:

-   **User Authentication API**

----------

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Abdul-Ikram/Django-API-LAB.git
cd Django-API-LAB

```

### 2. Set Up the Environment

#### Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate  # For macOS/Linux
.venv\Scripts\activate     # For Windows

```

#### Install dependencies:

```bash
pip install -r requirements.txt

```

#### Configure the `.env` file:

Add environment variables like `SECRET_KEY`, database settings, and email configurations in a `.env` file.

### 3. Apply Migrations

```bash
python manage.py migrate

```

### 4. Run the Server

```bash
python manage.py runserver

```

----------

## Postman Collection

To test the APIs, use the provided Postman collection.

1.  **Download the Postman Collection:**  
    The Postman collection file is located [here](https://github.com/Abdul-Ikram/Django-API-LAB/blob/main/PostDock/Boilerplates.postman_collection.json).
    
2.  **Import the Collection:**
    
    -   Open Postman.
    -   Click on `File > Import`.
    -   Select the `Boilerplates.postman_collection.json` file.
3.  **Environment Variables (Optional):**  
    Configure Postman variables to handle dynamic URLs and tokens.
    
    ```bash
    Key: boilerAccessToken
    Value: <Your access token>
    
    ```
    

----------

## Available APIs

### 1. User Authentication API

Handles user registration, login, email verification, and password reset functionalities.

-   **Documentation**: [User Authentication README](https://github.com/Abdul-Ikram/Django-API-LAB/blob/main/ReadMeNest/USER_AUTHENTICATION.md)
-   **Postman Folder**: `userflow/authentication` and `userflow/forgot-password`

----------

## Dynamic Additions

This repository is designed for scalability:

-   **New APIs:** Simply create a folder for your new API and add its documentation (e.g., `./<api-name>/README.md`).
-   **Postman Updates:** Update the Postman collection file (`Boilerplates.postman_collection.json`) as new endpoints are added.

----------

## Contributing

1.  Fork the repository.
2.  Create a new branch for your feature:
    
    ```bash
    git checkout -b feature/new-api
    
    ```
    
3.  Commit your changes:
    
    ```bash
    git commit -m "Add new API for <feature>"
    
    ```
    
4.  Push to your branch:
    
    ```bash
    git push origin feature/new-api
    
    ```
    
5.  Submit a pull request.

----------
