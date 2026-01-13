# CI/CD Pipeline with Docker and AWS EC2

## Overview
This project demonstrates a complete CI/CD pipeline that automatically builds a Docker image, pushes it to Docker Hub, and deploys the latest version to an AWS EC2 instance using GitHub Actions.

## Tech Stack
- GitHub Actions (CI/CD)
- Docker & Docker Hub
- AWS EC2 (Ubuntu)
- Nginx
- Linux

## CI/CD Workflow
1. Code is pushed to the `main` branch.
2. GitHub Actions triggers the pipeline.
3. Docker image is built using a Dockerfile.
4. Image is pushed to Docker Hub.
5. GitHub Actions connects to AWS EC2 via SSH.
6. Existing container is stopped and removed.
7. Latest Docker image is pulled and deployed automatically.

## Architecture
GitHub → GitHub Actions → Docker Hub → AWS EC2 → Docker Container

## Key Features
- Fully automated build and deployment
- Secure credential management using GitHub Secrets
- Dockerized application deployment
- Zero manual intervention after code push

## How to Run Locally
```bash
docker build -t devops-ci-cd-app .
docker run -d -p 8080:80 devops-ci-cd-app
