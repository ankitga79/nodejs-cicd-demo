## 📌 Project Description
This project demonstrates a fully automated **CI/CD pipeline** for a simple Node.js web application using:

- **GitHub Actions** for continuous integration and deployment
- **Docker** for containerization
- **DockerHub** for image registry

Whenever code is pushed to the `main` branch, GitHub Actions triggers a pipeline that:
1. Installs dependencies
2. Runs tests
3. Builds a Docker image
4. Logs in to DockerHub
5. Pushes the Docker image to DockerHub

---

## 🧰 Tech Stack
- **Node.js** (Backend App)
- **GitHub Actions** (CI/CD Workflow)
- **Docker** (Containerization)
- **DockerHub** (Image hosting)
- **Linux (Ubuntu)** (Development environment)

---

## 🛠️ CI/CD Pipeline Stages

| Stage            | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Checkout**     | Pulls the latest source code from the repository                           |
| **Install**      | Installs Node.js and app dependencies using `npm install`                  |
| **Test**         | Runs basic tests using `npm test`                                           |
| **Docker Build** | Builds the app into a Docker image using the provided `Dockerfile`         |
| **Docker Login** | Authenticates with DockerHub using GitHub Secrets                          |
| **Docker Push**  | Pushes the Docker image to DockerHub repo `ankitga79/nodejs-cicd-demo`     |

---

## 🔒 GitHub Secrets Used
To avoid exposing sensitive data in the repo, Docker credentials are stored as GitHub **repository secrets**:

- `DOCKER_USERNAME` → your DockerHub username
- `DOCKER_PASSWORD` → your DockerHub password or access token

---

## 📁 Repository Structure









---

## 🐳 Docker Image

- **Image Name:** `ankitga79/nodejs-cicd-demo`
- After each successful push to `main`, the latest image is published on DockerHub.

---

## ✅ How to Run the App via Docker

```bash
docker pull ankitga79/nodejs-cicd-demo
docker run -p 3000:3000 ankitga79/nodejs-cicd-demo

