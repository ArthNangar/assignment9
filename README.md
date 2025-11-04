# ⚡FastAPI Calculator with PostgreSQL & Docker Compose  

A lightweight, containerized calculator API built using **FastAPI**, integrated with **PostgreSQL** as the database, and **pgAdmin** as the GUI for SQL operations and administration.  
This project demonstrates how Docker Compose can streamline multi-service environments for modern backend applications.  

---

##  Key Features  

- RESTful API built with **FastAPI**
- Fully containerized using **Docker Compose**
- Persistent data storage via **PostgreSQL**
- Web interface rendered with **Jinja2 templates**
-  **pgAdmin 4** for database visualization and SQL query execution
-  Input validation handled with **Pydantic**
-  Error logging and robust exception handling

---

## 🧾 Prerequisites  

Before running the project, ensure you have the following installed:

- [Docker Desktop](https://www.docker.com/products/docker-desktop)  
- Docker Compose (included with Docker Desktop)  
- [Git](https://git-scm.com/) for version control (optional)

---

## 🗂️ Project Structure
```
.assignment9/
├── .github/
│ └── workflows/
│ └── test.yml ## GitHub Actions CI workflow
├── app/
│ ├── operations/
│ │ └── init.py
│ └── templates/
│ └── index.html 
├── tests/
│ ├── init.py
│ ├── conftest.py
│ ├── unit/
│ │ ├── init.py
│ │ └── test_calculator.py ## Unit tests for operations
│ ├── integration/
│ │ ├── init.py
│ │ └── test_fastapi_calculator.py ## Integration tests for FastAPI endpoints
│ └── e2e/
│ ├── init.py
│ └── test_e2e.py ## End-to-end tests (Playwright)
├── .gitignore
├── docker-compose.yml
├── Dockerfile
├── LICENSE
├── main.py ## Application entry point
├── pytest.ini
├── README.md
└── requirements.txt

```
## Getting Started  

### Clone the Repository  

```bash
git clone https://github.com/ArthNangar/assignment9.git
cd assignment9

Create Virtual Environment
python -m venv venv
source venv/bin/activate  
On Windows: venv\Scripts\activate


Install Dependencies
pip install -r requirements.txt

Run the Application
python main.py
Then open your browser at 👉 http://127.0.0.1:8000

```

## Docker Volumes
```
Docker volumes are used for data persistence:

postgres_data → Stores PostgreSQL data files

pgadmin_data → Retains pgAdmin configurations

Troubleshooting
🔹 Port Already in Use
If ports (8000 or 5432) are occupied, edit docker-compose.yml to map to different ports:

yaml
ports:
  - "8001:8000"
  - "5433:5432"
🔹 Database Connection Issues
docker compose ps
docker compose restart db
```

## CI/CD Pipeline

The GitHub Actions pipeline includes three stages:

1. **Test** - Executes all unit, integration, and end-to-end tests,  ensuring full coverage and stable functionality.
2. **Security** - Performs a vulnerability scan on the Docker image using Trivy, automatically failing the build if any critical or high-severity issues are detected.
3. **Deploy** - Builds and publishes multi-platform Docker images (for AMD64 and ARM64) to Docker Hub.

### Required GitHub Secrets
- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`

### Pipeline Features
- Automated test execution on every push and pull request
- Built-in container security scanning and quality gates
- Seamless, cross-platform image builds and deployment to Docker Hub



##  License
This project is licensed under the MIT License. See the LICENSE file for details.

##  Acknowledgments
FastAPI Documentation

Docker Docs

PostgreSQL Docs

pgAdmin Docs

## 👨‍💻 Author
Arth Nangar

Date: November 2025

Module 9 — Working with Raw SQL in pgAdmin