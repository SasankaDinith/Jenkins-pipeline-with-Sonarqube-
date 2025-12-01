## 🚀Project Overview

# 𝗔𝘂𝘁𝗼𝗺𝗮𝘁𝗲𝗱 𝗝𝗲𝗻𝗸𝗶𝗻𝘀 𝗖𝗜/𝗖𝗗 𝗣𝗶𝗽𝗲𝗹𝗶𝗻𝗲 𝘄𝗶𝘁𝗵 𝗦𝗼𝗻𝗮𝗿𝗾𝘂𝗯𝗲, 𝗗𝗼𝗰𝗸𝗲𝗿, 𝗚𝗶𝘁𝗵𝘂𝗯 𝗪𝗲𝗯𝗵𝗼𝗼𝗸𝘀 𝗮𝗻𝗱 𝗔𝗪𝗦


This repository contains the source and configuration for a production-like CI/CD pipeline built with Jenkins, SonarQube, Docker, GitHub Webhooks, and AWS EC2. The pipeline automates the path from code commit to deployment, enforcing quality gates and producing reproducible containerized builds.

 ![image url](https://github.com/SasankaDinith/Automated-Jenkins-CI-CD-Pipeline-with-Sonarqube-Docker-Github-Webhooks-and-AWS/blob/946a5a9bded50b2a1fa6cfcbe03749785d93e64b/assets/README%20img/project%20diagram.png)

## 🔑 Key features:

- 🖥️ Git & GitHub – Version control + repo management
- ⚙️ Jenkins – Orchestrates the entire CI/CD process
- 🔔 GitHub Webhooks – Triggers pipeline on every push
- 🔍 SonarQube – Code quality & security scanning
- 🐳 Docker – Packaging and consistent deployment
- ☁️ AWS EC2 – Three instances hosting Jenkins, SonarQube & Docker nodes


## 🔄 Pipeline Workflow (End-to-End)

- Developer commits code → GitHub Repository
- GitHub Webhook → Notifies Jenkins instantly
- Build Stage → Jenkins pulls the repo & compiles
- Quality Gate → SonarQube scans for issues
- Docker Build → Image creation + tagging
- Push/Deploy → Deployed into AWS EC2 automatically <br/>

<p>  The entire pipeline is designed to be fully re-runnable and scalable. </p>

## Prerequisites:

- GitHub repository for the application
- Jenkins server with plugins: Pipeline, GitHub, Docker Pipeline, SonarQube Scanner, Credentials Binding
- SonarQube server reachable from Jenkins
- Docker installed on build/deploy hosts
- AWS account with EC2 instances (Jenkins, SonarQube optional, Docker host)
- Configured GitHub Webhook pointing to Jenkins


## 🛠️ 𝗧𝗲𝗰𝗵 𝗦𝘁𝗮𝗰𝗸:
Git &nbsp;&nbsp;| &nbsp;&nbsp;GitHub &nbsp;&nbsp;| &nbsp;&nbsp;Jenkins &nbsp;&nbsp;| &nbsp;&nbsp;Docker &nbsp;&nbsp;| &nbsp;&nbsp;SonarQube &nbsp;&nbsp;| &nbsp;&nbsp;GitHub Webhooks &nbsp;&nbsp;| &nbsp;&nbsp;NGINX Ingress &nbsp;&nbsp;| &nbsp;&nbsp;AWS EC2

