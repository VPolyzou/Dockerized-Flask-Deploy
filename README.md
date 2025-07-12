# CI/CD Pipeline for a Dockerized Flask App

This project demonstrates a simple CI/CD pipeline using Jenkins to build and deploy a Dockerized Flask application.

## 📦 Technologies
- Python 3 (Flask)
- Docker
- Jenkins (Declarative Pipeline)

## 📂 Project Structure
- `app.py` → The Flask web application
- `Dockerfile` → Instructions to containerize the Flask app
- `Jenkinsfile` → CI/CD pipeline to build & run the Docker container

## 🚀 How it Works

1. Jenkins checks out the code from this repository.
2. Builds a Docker image for the Flask app.
3. Stops and removes any existing container named `flask-app`.
4. Runs a new container from the built image, exposing port 5000.

## 🖥️ Run Locally

```bash
docker build -t my-flask-app .
docker run -d -p 5000:5000 --name flask-app my-flask-app
