# 𝗔𝘂𝘁𝗼𝗺𝗮𝘁𝗲𝗱 𝗝𝗲𝗻𝗸𝗶𝗻𝘀 𝗖𝗜/𝗖𝗗 𝗣𝗶𝗽𝗲𝗹𝗶𝗻𝗲 𝘄𝗶𝘁𝗵 𝗦𝗼𝗻𝗮𝗿𝗾𝘂𝗯𝗲, 𝗗𝗼𝗰𝗸𝗲𝗿, 𝗚𝗶𝘁𝗵𝘂𝗯 𝗪𝗲𝗯𝗵𝗼𝗼𝗸𝘀 𝗮𝗻𝗱 𝗔𝗪𝗦


This repository contains the source and configuration for a production-like CI/CD pipeline built with Jenkins, SonarQube, Docker, GitHub Webhooks, and AWS EC2. The pipeline automates the path from code commit to deployment, enforcing quality gates and producing reproducible containerized builds.

 ![image url](https://github.com/SasankaDinith/Automated-Jenkins-CI-CD-Pipeline-with-Sonarqube-Docker-Github-Webhooks-and-AWS/blob/946a5a9bded50b2a1fa6cfcbe03749785d93e64b/assets/README%20img/project%20diagram.png)

 
## Table of Contents
- [🚀Project Overview](#🚀Project-overview)
- [Key features](#key-features)
- [Pipeline Workflow](#pipeline-workflow)
- [Prerequisites](#prerequisites)
- [Tech Stack](#Tech-Stack)
- [Setup instrctions](#setup-instructions)
  - [1. Launch EC2 Instances on AWS](#1-Launch-EC2-instances-on-AWS)
  - [2. Create an SSH Connection Between Jenkins EC2 and Docker EC2](#2-Create-an-SSH-connection-between-Jenkins-EC2-and-Docker-EC2)
  - [3. Configure Jenkins Plugins and Jobs](#3-Configure-Jenkins-Plugins-and-Jobs)
  - [4. Build a Docker Container and Deploy it](#4-Build-a-Docker-container-and-Deploy-it)
- [What I learned](#what-i-learned)
- [Next steps](#Next-steps)
- [Licence](#licence)


##  🚀Project Overview
 - Trigger builds on every GitHub push via Webhooks
 - Run SonarQube static analysis and Quality Gates
 - Build & tag Docker images automatically
 - Deploy containers to AWS EC2 (or pull from registry)
 - Improve release velocity and enforce code quality

 --- 
## Key features

- 🖥️ Git & GitHub – Version control + repo management
- ⚙️ Jenkins – Orchestrates the entire CI/CD process
- 🔔 GitHub Webhooks – Triggers pipeline on every push
- 🔍 SonarQube – Code quality & security scanning
- 🐳 Docker – Packaging and consistent deployment
- ☁️ AWS EC2 – Three instances hosting Jenkins, SonarQube & Docker nodes

---

## Pipeline Workflow

- Developer commits code → GitHub Repository
- GitHub Webhook → Notifies Jenkins instantly
- Build Stage → Jenkins pulls the repo & compiles
- Quality Gate → SonarQube scans for issues
- Docker Build → Image creation + tagging
- Push/Deploy → Deployed into AWS EC2 automatically <br/>

<p>  The entire pipeline is designed to be fully re-runnable and scalable. </p>

--- 

## Prerequisites

- GitHub repository for the application
- Jenkins server with plugins: Pipeline, GitHub, Docker Pipeline, SonarQube Scanner, Credentials Binding
- SonarQube server reachable from Jenkins
- Docker installed on build/deploy hosts
- AWS account with EC2 instances (Jenkins, SonarQube optional, Docker host)
- Configured GitHub Webhook pointing to Jenkins

---

## Tech Stack:
Git &nbsp;&nbsp;| &nbsp;&nbsp;GitHub &nbsp;&nbsp;| &nbsp;&nbsp;Jenkins &nbsp;&nbsp;| &nbsp;&nbsp;Docker &nbsp;&nbsp;| &nbsp;&nbsp;SonarQube &nbsp;&nbsp;| &nbsp;&nbsp;GitHub Webhooks &nbsp;&nbsp;| &nbsp;&nbsp;NGINX Ingress &nbsp;&nbsp;| &nbsp;&nbsp;AWS EC2

--- 

## Setup Instructions

### 1) Launch EC2 Instances on AWS

Three EC2 instances are used to host the following servers:

- Jenkins Server → Builds an automated pipeline and includes plugins such as SonarQube and SSH2 Easy.
- Docker Server → Deploys the website and makes it accessible to end users.
- SonarQube Server → Performs code quality and security checks.


<p>Each EC2 instance is configured with the necessary dependencies and plugins.<p/>

### 2) Create an SSH Connection Between Jenkins EC2 and Docker EC2

- Generate SSH keys on the Jenkins server:
``` bash
  ssh-keygen -t rsa
```

- Copy the SSH key to the Docker EC2 instance using its public IP address for passwordless authentication:
``` bash
  ssh-copy-id ubuntu@<ip-address>
```

### 3) Configure Jenkins Plugins and Jobs

- Install the SSH2 Easy plugin in Jenkins to manage secure SSH connections.
- Set up server groups and sites for Jenkins, SonarQube, and Docker.
- Create a Jenkins job:

   - Add the GitHub repository link.
   - Specify the branch to build and deploy.
   - Add build steps to copy code from Jenkins to SonarQube and Docker instances.
 
### 4) Build a Docker Container and Deploy it

- Create a Dockerfile and run the following commands:
  ``` bash
  docker build -t automated-pipeline .
  ```

  ``` bash
  docker run -d --name custom-container -p 8085:80 automated-pipeline
  ```
 ---

 
## What I learned

 - Real-world pipeline debugging (tokens, credentials, agent configs)
 - SonarQube quality gates and their role in CI
 - Docker image lifecycle and deployment considerations
 - Basic cloud deployments and ingress configuration


--- 

## Next steps

 - Move images to AWS ECR
 - Use Terraform for infrastructure-as-code
 - Switch to Kubernetes (EKS) for orchestration
 - Add Slack/Teams notifications and rollback strategies

--- 

## Licence

<p>This project is licensed under the MIT License.<p/>













