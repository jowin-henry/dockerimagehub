
---

# Flask Docker CI/CD App

This is a simple **Flask** web application that returns "Hello World!" when accessed at the root URL (`/`). The project uses **Docker** for containerization and **GitHub Actions** for CI/CD.

---

## 🧱 Project Structure

```

.
├── app.py             # Flask app
├── test\_app.py        # Pytest test script
├── DockerFile         # Docker instructions
├── cicd.yml           # GitHub Actions workflow
└── README.md          # Project documentation

````

---

## 🚀 Running Locally

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/flask-docker-cicd.git
cd flask-docker-cicd
````

### 2. Create a Virtual Environment (optional)

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install flask pytest
```

### 4. Run the App

```bash
python app.py
```

Visit: `http://localhost:5000`

---

## 🧪 Running Tests

```bash
pytest test_app.py
```

---

## 🐳 Docker Usage

### 1. Build the Docker Image

```bash
docker build -t flask-docker-app -f DockerFile .
```

### 2. Run the Container

```bash
docker run -p 5000:5000 flask-docker-app
```

Visit: `http://localhost:5000`

---

## 🔁 CI/CD Pipeline (GitHub Actions)

### Workflow: `.github/workflows/cicd.yml`

Triggered on:

* Push or pull request to `main` branch

#### Pipeline Stages:

1. **Build Docker image** (non-published test)
2. **Run Python tests** using `pytest`
3. **Build & Publish Docker image to Docker Hub**

> Ensure that the following secrets are configured in your GitHub repository:

* `DOCKER_USERNAME`
* `DOCKER_PASSWORD`

---

## 📦 DockerHub Image

Once published, you can pull the image using:

```bash
docker pull <your-dockerhub-username>/flasktest-app:latest
```

---

