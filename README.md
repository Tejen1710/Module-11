# FastAPI Secure User Management

## Overview
This project is a FastAPI-based application designed for secure user management. It includes features such as user creation, password hashing, and secure authentication. The project is structured to ensure scalability and maintainability.

## Project Structure

### `app/`
- **`__init__.py`**: Initializes the app module.
- **`main.py`**: Contains the FastAPI application and routes for user management.
- **`database.py`**: Configures the database connection and session management.
- **`models.py`**: Defines the database models, including the `User` model.
- **`schemas.py`**: Defines Pydantic schemas for request validation and response serialization.
- **`security.py`**: Handles password hashing and verification using `passlib`.
- **`crud.py`**: Implements database operations for user management.

### `tests/`
- **`__init__.py`**: Initializes the tests module.
- **`test_security.py`**: Tests password hashing and verification.
- **`test_schemas.py`**: Tests Pydantic schema validation.
- **`test_users_api.py`**: Tests the user management API endpoints.

### `.github/workflows/`
- **`ci.yml`**: Defines the CI/CD pipeline for testing and deployment using GitHub Actions.

### Root Files
- **`Dockerfile`**: Docker configuration for containerizing the application.
- **`docker-compose.yml`**: Optional file for local development with Docker Compose.
- **`requirements.txt`**: Lists the Python dependencies for the project.
- **`README.md`**: Provides an overview of the project.
- **`reflection.md`**: Placeholder for project reflections or notes.

## Features
- User creation with hashed passwords.
- Secure password verification.
- RESTful API endpoints for user management.
- Database integration with SQLAlchemy.
- Pydantic for data validation.
- Unit tests for security, schemas, and API endpoints.
- CI/CD pipeline for automated testing and deployment.

## Getting Started

### Prerequisites
- Python 3.11
- Docker (optional, for containerized development)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Tejen1710/module-10.git
   cd module-10
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Application
1. Start the application:
   ```bash
   uvicorn app.main:app --host 0.0.0.0 --port 8000
   ```
2. Access the API documentation at `http://127.0.0.1:8000/docs`.

### Running Tests
Run the tests using:
```bash
pytest
```

#### Setting Up Database for Testing

For **local development** with SQLite (default):
```bash
pytest
```

For **Postgres integration tests**, set the `DATABASE_URL` environment variable:
```bash
# PowerShell
$env:DATABASE_URL = "postgresql://user:password@localhost:5432/calculator_test"
pytest

# Or on Linux/macOS
export DATABASE_URL="postgresql://user:password@localhost:5432/calculator_test"
pytest
```

To run only unit tests:
```bash
pytest tests/unit/
```

To run only integration tests:
```bash
pytest tests/integration/
```

#### Module 11: Calculation Service

This module includes:
- **Calculation Model** (`app/models/calculation.py`): SQLAlchemy ORM model with user relationship
- **Calculation Schemas** (`app/schemas/calculation.py`): Pydantic schemas with CalcType enum and validation
- **Factory Pattern** (`app/services/factory.py`): Operation classes (Add, Sub, Multiply, Divide) with CalculationFactory
- **Unit Tests** (`tests/unit/`): Tests for factory operations and schema validation
- **Integration Tests** (`tests/integration/`): Tests for database operations

Supported calculation types: `Add`, `Sub`, `Multiply`, `Divide`

Docker Hub Image: https://hub.docker.com/r/tejenthakkar1710/fastapi-secure-users
1. Build the Docker image:
   ```bash
   docker build -t fastapi-secure-users .
   ```
    The Docker image for this project is available at:

    https://hub.docker.com/r/tejenthakkar1710/fastapi-secure-users

2. Run the Docker container:
   ```bash
   docker run -p 8000:8000 fastapi-secure-users
   ```

## License
This project is licensed under the MIT License.