
# Potential Broccoli

## Overview

**Potential Broccoli** is a user management API built with FastAPI and a MariaDB database. The project implements user registration and authorization features, using JWT tokens for securing subsequent requests. It is designed with a modular architecture, making it easy to extend and maintain.

## Features

- **User Registration:** Users can sign up with an email, username, and password.
- **User Authentication:** Users can log in to obtain a JWT token.
- **Token Verification:** Secured routes that verify JWT tokens for authorized access.
- **Modular Design:** Code is organized into distinct modules for easy maintenance and scalability.

## Project Structure

The project is organized into the following structure:

```
C:.
|   .gitignore
|   docker-compose.yml
|   DockerFile
|   main.py
|   project_structure.txt
|   README.md
|   requirements.txt
|   
+---app
|   +---application
|   |   +---services
|   |   |   user_service.py
|   |   
|   +---domain
|   |   +---models
|   |   |   user.py
|   |   +---schemas
|   |   |   user_schemas.py
|   |   +---security
|   |   |   hashing.py
|   |   +---utils
|   |   
|   +---infrastructure
|   |   +---database
|   |   |   db.py
|   |   +---repositories
|   |   |   user_repository.py
|   |   
|   \---presentation
|       +---api
|       |   +---v1
|       |       +---user
|       |           user_routes.py
|       +---dependencies
|           
```

### Key Components:

- **`application/services`:** Contains the business logic of the application. Here, you can define various services that interact with the repositories and provide functionalities to the API routes.

- **`domain/models`:** Defines the database models used for the application, representing the structure of the data stored in MariaDB.

- **`domain/schemas`:** Includes Pydantic schemas used for data validation and serialization.

- **`domain/security`:** Implements security features such as password hashing.

- **`infrastructure/database`:** Manages database connections and interactions with the database.

- **`infrastructure/repositories`:** Contains repository classes responsible for data access, following the repository pattern to abstract database operations.

- **`presentation/api`:** Implements the API routes, organized by version and functionality.

## Setup Instructions

### Prerequisites

Ensure you have the following installed on your machine:

- **Python 3.12+**
- **Docker** and **Docker Compose**

### Step 1: Create a Virtual Environment

Navigate to your project directory and create a virtual environment:

```bash
cd /path/to/Potential-Broccoli
python -m venv venv
```

### Step 2: Activate the Virtual Environment

Activate the virtual environment with the following command:

- **On Windows:**

```bash
.\venv\Scripts\activate
```

- **On macOS/Linux:**

```bash
source venv/bin/activate
```

### Step 3: Install Requirements

Once the virtual environment is activated, install the necessary Python packages:

```bash
pip install -r requirements.txt
```

### Step 4: Run Docker Compose

To set up the MariaDB database, you need to run Docker Compose:

```bash
docker-compose up -d
```

This command will start the database container in the background.

### Step 5: Run the Application

With the Docker containers running, you can start the FastAPI application:

```bash
uvicorn main:app --reload
```

You can now access the API documentation at `http://127.0.0.1:8000/docs`.

## Architecture Explanation

### Modular Design

The project is structured into multiple modules, which promotes separation of concerns. Each module has a specific responsibility, making the codebase easier to understand, maintain, and extend. This design also allows for scalability, enabling you to add new features or modify existing ones without affecting unrelated components.

### FastAPI Framework

FastAPI is a modern web framework for building APIs with Python, offering several benefits:

- **Performance:** FastAPI is built on Starlette, making it one of the fastest frameworks available.
- **Automatic Documentation:** It automatically generates interactive API documentation (Swagger UI) using OpenAPI.
- **Pydantic Integration:** FastAPI uses Pydantic for data validation, which ensures that the input data conforms to expected types and formats.

### MariaDB Database

MariaDB is a powerful and reliable open-source relational database. In this project, it stores user data securely, ensuring efficient data retrieval and manipulation.

### JWT for Authentication

JWT (JSON Web Tokens) is used for user authentication and securing routes. After successful login, users receive a token that must be included in the header of subsequent requests to access protected endpoints.

## Conclusion

The **Potential Broccoli** project is a well-structured user management API that utilizes modern technologies and practices. It is designed for maintainability, scalability, and security, making it an excellent foundation for further development.

Feel free to contribute to this project by suggesting features or improvements!

### Notes
- This `README.md` provides clear instructions on setting up the project and explains the architecture and technologies used. You can customize it further based on your specific requirements or project updates.
- Make sure to adjust any paths or specifics that may need changes depending on your actual setup or additional features you may implement.