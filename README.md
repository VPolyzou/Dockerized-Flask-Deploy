CI/CD Pipeline for a Dockerized Flask App
This project demonstrates a simple CI/CD pipeline using Jenkins to build and deploy a Dockerized Flask application. Additionally, it includes an Ansible playbook and inventory file for automating deployment on target servers.

📦 Technologies
Python 3 (Flask)

Docker

Jenkins (Declarative Pipeline)

Ansible (for deployment automation)

📂 Project Structure
app.py → The Flask web application

Dockerfile → Instructions to containerize the Flask app

Jenkinsfile → CI/CD pipeline to build & run the Docker container

inventory.ini → Ansible inventory file with target servers

deploy_flask_app.yaml → Ansible playbook for deployment

🚀 How it Works
Jenkins Pipeline
Jenkins checks out the code from this repository.

Builds a Docker image for the Flask app.

Stops and removes any existing container named flask-app.

Runs a new container from the built image, exposing port 5000.

Ansible Deployment
Uses inventory.ini to define target servers.

The playbook deploy_flask_app.yaml installs Docker on targets if needed, clones the application repo, builds the Docker image, and runs the container on the remote hosts.

🖥️ Run Locally
To build and run the Docker container manually:
docker build -t my-flask-app .
docker run -d -p 5000:5000 --name flask-app my-flask-app

⚙️ Deploy with Ansible
Make sure you have SSH access to your target servers defined in inventory.ini.

Run the playbook to deploy the app:
ansible-playbook -i inventory.ini deploy_flask_app.yaml
