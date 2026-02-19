# task-manager-api

A RESTful task management API built with **Python (FastAPI)** and **PostgreSQL**, containerized with **Docker** and automated with **GitHub Actions CI/CD**.

> Personal project to practice backend development, database design, and DevOps best practices.

---

## Features

- **CRUD operations** for tasks and users
- **JWT authentication** with token-based access control
- **PostgreSQL** database with SQLAlchemy ORM
- **Pydantic** data validation and serialization
- **Docker Compose** for local development
- **GitHub Actions** CI pipeline with automated tests
- Auto-generated **OpenAPI docs** at `/docs`

---

## Tech Stack

| Layer | Technology |
|------------|---------------------|
| Language | Python 3.11 |
| Framework | FastAPI |
| Database | PostgreSQL + SQLAlchemy |
| Auth | JWT (python-jose) |
| Testing | pytest |
| Container | Docker + Docker Compose |
| CI/CD | GitHub Actions |

---

## Project Structure

```
task-manager-api/
├── app/
│   ├── main.py           # FastAPI app entry point
│   ├── models/           # SQLAlchemy ORM models
│   ├── routers/          # API route handlers
│   ├── schemas/          # Pydantic request/response schemas
│   ├── core/             # Config, auth, dependencies
│   └── database.py       # DB connection setup
├── tests/                # pytest test suite
├── .github/workflows/    # GitHub Actions CI config
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
└── README.md
```

---

## Getting Started

### Prerequisites
- Docker & Docker Compose
- Python 3.11+

### Run with Docker

```bash
git clone https://github.com/benisnotitdog/task-manager-api.git
cd task-manager-api
docker-compose up --build
```

API will be available at `http://localhost:8000`
Swagger docs at `http://localhost:8000/docs`

### Run locally

```bash
pip install -r requirements.txt
uvicorn app.main:app --reload
```

---

## API Endpoints

| Method | Endpoint | Description |
|--------|-------------------|----------------------------|
| POST | /auth/register | Register a new user |
| POST | /auth/login | Login and get JWT token |
| GET | /tasks | List all tasks |
| POST | /tasks | Create a new task |
| GET | /tasks/{id} | Get a task by ID |
| PUT | /tasks/{id} | Update a task |
| DELETE | /tasks/{id} | Delete a task |

---

## CI Pipeline

Every push triggers the GitHub Actions workflow:
1. Lint with `flake8`
2. Run `pytest` test suite
3. Build Docker image

---

## What I Learned

- Designing RESTful API with proper HTTP semantics
- Writing clean, testable Python code
- Database schema design and ORM usage
- Containerizing applications with Docker
- Setting up automated CI pipelines

---

*Part of my learning journey toward full-stack software development.*
