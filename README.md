##Architecture

                    ┌────────────────────────────┐
                    │        End User            │
                    │  Web Browser / Client      │
                    └─────────────┬──────────────┘
                                  │  HTTP (port e.g. 80 / 3000)
                                  ▼
                    ┌────────────────────────────┐
                    │      AWS EC2 Instance      │
                    │  (Amazon Linux / Ubuntu)   │
                    │  - Docker Engine           │
                    └─────────────┬──────────────┘
                                  │
                                  ▼
                    ┌────────────────────────────┐
                    │   Node.js Web App in       │
                    │      Docker Container      │
                    ├────────────────────────────┤
                    │  - Built from Dockerfile   │
                    │  - Runs app.js (Express)   │
                    │  - Exposes HTTP port       │
                    └────────────────────────────┘


The goal is to show a complete workflow from code commit → container build → deployment on a cloud server.

🔍 Project Overview

Backend: Node.js application (app.js) serving a simple web page or API.

Containerization: Docker image built from the provided Dockerfile.

Infrastructure: AWS EC2 instance running Docker as the hosting environment.

CI/CD: GitHub Actions workflow (under .github/) that builds and deploys the app automatically on every push.

This is a good portfolio project to demonstrate basic cloud, Docker, and CI/CD skills.

🎯 Objectives

Package a Node.js app into a Docker container.

Deploy and run the container on an AWS EC2 instance.

Use GitHub Actions to automate:

Code checkout

Docker image build

Remote deployment to EC2

🧩 Key Components

app.js
Main Node.js application file (HTTP server / Express app).

Dockerfile
Defines how the Node.js application is containerized, including:

Base Node.js image

Copying source code

Installing dependencies

Exposing a port

Starting the app

.github/
GitHub Actions workflow configuration for CI/CD:

Automatically runs on code push or pull request.

Builds the Docker image.

Deploys the updated app to AWS EC2 (for example via SSH and Docker commands).

package.json
Node.js metadata and dependencies.

🛠 Tech Stack

Language / Runtime: Node.js, JavaScript

Containerization: Docker

Cloud Provider: AWS EC2

CI/CD: GitHub Actions

Source Control: GitHub
