# Cloud-Native Complaint Management System

A cloud-native complaint management system with end-to-end DevOps automation, demonstrating modern DevOps practices including CI/CD, containerization, orchestration, and Infrastructure as Code.

## 🏗️ Architecture

- **Backend**: Flask (Python) REST API
- **Database**: PostgreSQL
- **Containerization**: Docker + Docker Compose
- **CI/CD**: GitHub Actions
- **Orchestration**: Kubernetes (Minikube)
- **IaC**: Terraform + Ansible

## 📁 Project Structure

```
complaint-management-system/
├── app/                        # Flask application
│   ├── app.py                  # Main application
│   ├── requirements.txt        # Python dependencies
│   ├── templates/              # HTML templates
│   │   └── index.html
│   └── tests/                  # Unit tests
│       └── test_app.py
├── Dockerfile                  # Container image definition
├── docker-compose.yml          # Multi-container orchestration
├── .github/workflows/          # CI/CD pipeline
│   └── ci-cd.yml
├── k8s/                        # Kubernetes manifests
│   ├── namespace.yml
│   ├── postgres-deployment.yml
│   ├── postgres-service.yml
│   ├── app-deployment.yml
│   └── app-service.yml
├── terraform/                  # Infrastructure as Code
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
└── ansible/                    # Configuration Management
    ├── playbook.yml
    └── inventory.ini
```

## 🚀 Quick Start

### Prerequisites
- Docker & Docker Compose
- Python 3.11+
- Minikube (for Kubernetes)
- Terraform (for IaC)
- Ansible (for configuration management)

### Run with Docker Compose
```bash
docker-compose up --build
```
Access the app at `http://localhost:5000`

### Run on Kubernetes (Minikube)
```bash
minikube start
kubectl apply -f k8s/namespace.yml
kubectl apply -f k8s/
kubectl port-forward -n complaint-app svc/flask-app-service 5000:5000
```

## 🔄 CI/CD Pipeline

The GitHub Actions pipeline automatically:
1. **Builds** the Docker image on every push
2. **Runs tests** using pytest
3. **Pushes** the image to Docker Hub on merge to `main`

## 📊 API Endpoints

| Method | Endpoint      | Description            |
|--------|---------------|------------------------|
| GET    | `/`           | Web UI                 |
| GET    | `/health`     | Health check           |
| GET    | `/complaints` | List all complaints    |
| POST   | `/complaints` | Submit a new complaint |

## 🧪 Running Tests
```bash
cd app
pip install -r requirements.txt
pytest tests/ -v
```

## 📝 Branch Strategy
- `main` — Production-ready code
- `dev` — Development/integration branch
- `feature/*` — Feature branches for new development

## 👤 Author
DevOps Project — Cloud-Native Complaint Management System
