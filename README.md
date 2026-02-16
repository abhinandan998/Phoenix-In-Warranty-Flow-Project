# 🚀 Postman API Automation Integration with GitHub Actions and Jenkins

<div align="center">

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)

**A robust CI/CD pipeline for automated API testing using Postman, Newman, and GitHub Actions**

[View Live Report](https://abhinandan998.github.io/Phoenix-In-Warranty-Flow-Project/) • [Report an Issue](https://github.com/abhinandan998/Phoenix-In-Warranty-Flow-Project/issues) • [Request Feature](https://github.com/abhinandan998/Phoenix-In-Warranty-Flow-Project/issues)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Testing Coverage](#-testing-coverage)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [CI/CD Integration](#-cicd-integration)
  - [GitHub Actions](#-github-actions-workflow)
  - [Jenkins Pipeline](#-jenkins-pipeline)
- [Viewing Reports](#-viewing-reports)
- [Configuration](#-configuration)
- [About the Author](#-about-the-author)
- [Contributing](#-contributing)

---

## 🎯 Overview

This repository demonstrates a comprehensive **Proof of Concept (POC)** for integrating Postman API tests with multiple CI/CD platforms including **GitHub Actions** and **Jenkins**. The project showcases automated API testing with comprehensive reporting, scheduled execution, parallel test execution, and seamless CI/CD integration across different platforms.

### 🌟 What Makes This Project Special?

- ✅ **Multi-Platform CI/CD**: Supports both GitHub Actions and Jenkins pipelines
- ⚡ **Parallel Execution**: Run multiple test collections simultaneously for faster results
- 🖥️ **Distributed Testing**: Master-agent architecture with EC2 instances
- 📊 **Beautiful HTML Reports**: Generated with newman-reporter-htmlextra
- 📧 **Email Notifications**: Automated test reports sent via Gmail SMTP
- 🌐 **Live Report Viewing**: Reports published to GitHub Pages for easy access
- ⏰ **Scheduled Execution**: Cron-based automated test runs on both platforms
- 🔒 **Secure**: Secrets management with GitHub Secrets and Jenkins credentials
- 🎯 **Comprehensive Testing**: Happy flows, negative scenarios, and edge cases

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🔄 **Multi-Platform CI/CD** | Supports both GitHub Actions and Jenkins pipelines |
| ⚡ **Parallel Execution** | Run multiple collections simultaneously on Jenkins |
| 🖥️ **Master-Agent Architecture** | Distributed testing across EC2 Master and Agent nodes |
| 📈 **Detailed Reporting** | HTML reports with test results, assertions, and response times |
| 📧 **Email Notifications** | Automatic delivery of test reports to team members |
| 🌐 **GitHub Pages** | Live, always-accessible test reports |
| ⏱️ **Scheduled Runs** | Cron-based automated testing on both platforms |
| 📦 **Artifact Storage** | Test reports archived for team download |
| 🔐 **Security First** | Environment variables and secrets properly managed |
| 🖥️ **Self-Hosted Runner** | AWS EC2 instances for enhanced control and performance |

---

## 🧪 Testing Coverage

This project implements comprehensive API testing strategies:

### Test Types

- ✅ **Happy Flow Testing** - Validates successful API responses and workflows
- ❌ **Negative Testing** - Tests error handling and invalid inputs
- 🔍 **Edge Case Testing** - Boundary value and corner case validation
- 🔑 **Token Testing** - Authentication and authorization validation
- 📊 **Data-Driven Testing** - CSV-based test data management
- 📝 **Schema Validation** - Response structure verification
- 🔒 **Secrets Management** - Secure handling of sensitive data with GitHub Secrets

---

## 🛠️ Tech Stack

<table>
<tr>
<td align="center" width="20%">
<img src="https://www.vectorlogo.zone/logos/getpostman/getpostman-icon.svg" width="48" height="48" alt="Postman" />
<br><strong>Postman</strong>
<br><sub>API Testing</sub>
</td>
<td align="center" width="20%">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" width="48" height="48" alt="Node.js" />
<br><strong>Node.js v22/24</strong>
<br><sub>Runtime Environment</sub>
</td>
<td align="center" width="20%">
<img src="https://avatars.githubusercontent.com/u/7647292?s=200&v=4" width="48" height="48" alt="Newman" />
<br><strong>Newman</strong>
<br><sub>CLI Runner</sub>
</td>
<td align="center" width="20%">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/github/github-original.svg" width="48" height="48" alt="GitHub Actions" />
<br><strong>GitHub Actions</strong>
<br><sub>CI/CD Pipeline</sub>
</td>
<td align="center" width="20%">
<img src="https://www.vectorlogo.zone/logos/jenkins/jenkins-icon.svg" width="48" height="48" alt="Jenkins" />
<br><strong>Jenkins</strong>
<br><sub>CI/CD Server</sub>
</td>
</tr>
<tr>
<td align="center" width="20%">
<strong>newman-reporter-htmlextra</strong>
<br><sub>HTML Reporting</sub>
</td>
<td align="center" width="20%">
<strong>Gmail SMTP</strong>
<br><sub>Email Notifications</sub>
</td>
<td align="center" width="20%">
<strong>GitHub Pages</strong>
<br><sub>Report Hosting</sub>
</td>
<td align="center" width="20%">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" width="48" height="48" alt="AWS" />
<br><strong>AWS EC2</strong>
<br><sub>Master & Agent Servers</sub>
</td>
<td align="center" width="20%">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" width="48" height="48" alt="Linux" />
<br><strong>Linux/Ubuntu</strong>
<br><sub>Server OS</sub>
</td>
</tr>
</table>

---

## 🏗️ Architecture

This project implements a scalable, distributed testing architecture across multiple platforms:

### GitHub Actions Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     GitHub Repository                        │
│  ┌──────────────────────────────────────────────────────┐   │
│  │                  Push to Main Branch                  │   │
│  │                 Manual Trigger (workflow_dispatch)    │   │
│  │                 Scheduled Cron Jobs                   │   │
│  └──────────────────┬───────────────────────────────────┘   │
│                     ▼                                        │
│  ┌──────────────────────────────────────────────────────┐   │
│  │           GitHub Actions Runner (Ubuntu VM)          │   │
│  │  • Install Newman & Dependencies                     │   │
│  │  • Execute Postman Collections                       │   │
│  │  • Generate HTML Reports                             │   │
│  └──────────────────┬───────────────────────────────────┘   │
│                     ▼                                        │
│  ┌──────────────────────────────────────────────────────┐   │
│  │                Report Distribution                    │   │
│  │  ├─► Artifacts (Download)                            │   │
│  │  ├─► GitHub Pages (Live View)                        │   │
│  │  └─► Email (Gmail SMTP)                              │   │
│  └──────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

### Jenkins Master-Agent Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                           Jenkins Setup                             │
│                                                                      │
│  ┌────────────────────────────────────────────────────────────┐    │
│  │                    EC2 Master Server                        │    │
│  │                  (Jenkins Controller)                       │    │
│  │                                                              │    │
│  │  • Orchestrates pipeline execution                          │    │
│  │  • Manages job scheduling (Cron)                           │    │
│  │  • Collects & merges reports                               │    │
│  │  • Sends email notifications                               │    │
│  └────────────────────┬───────────────────────────────────────┘    │
│                       │                                              │
│                       ▼ (Parallel Execution)                        │
│         ┌─────────────┴─────────────┐                              │
│         ▼                           ▼                               │
│  ┌──────────────┐           ┌──────────────┐                       │
│  │  Any Agent   │           │ EC2 Postman  │                       │
│  │              │           │    Agent     │                       │
│  │ Collection 1 │           │ Collection 2 │                       │
│  │              │           │              │                       │
│  │ • Checkout   │           │ • Checkout   │                       │
│  │ • Newman     │           │ • Newman     │                       │
│  │ • Report Gen │           │ • Report Gen │                       │
│  │ • Stash      │           │ • Stash      │                       │
│  └──────────────┘           └──────────────┘                       │
│         │                           │                               │
│         └─────────────┬─────────────┘                              │
│                       ▼                                             │
│  ┌────────────────────────────────────────────────────────────┐   │
│  │            Report Aggregation & Distribution                │   │
│  │  • Unstash all reports                                      │   │
│  │  • Archive artifacts                                        │   │
│  │  • Send email with attachments                             │   │
│  └────────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────────┘
```

### Key Architecture Benefits

- **🚀 Parallel Execution**: Multiple collections run simultaneously on different agents
- **⚖️ Load Distribution**: Work distributed across master and agent nodes
- **📈 Scalability**: Easy to add more agents for increased capacity
- **🔄 Redundancy**: Multiple CI/CD platforms ensure reliability
- **⚡ Speed**: Parallel execution reduces total test time significantly

---

## 📁 Project Structure

```
Phoenix-In-Warranty-Flow-Project/
│
├── 📄 In-Warranty Flow Collection.postman_collection.json   # Postman collection with API tests
├── 🌍 QA.postman_environment.json                          # Environment variables and configurations
├── 📊 testData.csv                                         # Test data for data-driven testing
├── 📋 README.md                                            # Project documentation
├── 📜 Jenkinsfile                                          # Jenkins pipeline configuration
├── ⚙️ .github/
│   └── workflows/                                          # GitHub Actions workflow files
│       ├── main.yml                                        # Main workflow
│       └── scheduled.yml                                   # Scheduled workflow (cron)
└── 📂 newman/                                              # Generated test reports (auto-created)
    ├── index.html                                          # Main HTML test report
    ├── Collection1_Report.html                             # Parallel collection 1 report
    └── Collection2_Report.html                             # Parallel collection 2 report
```

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v22 or higher) - [Download here](https://nodejs.org/en)
- **npm** (comes with Node.js)
- **Git** - For cloning the repository

### 📥 Installation

Follow these steps to set up the project on your local machine:

#### 1️⃣ Clone the Repository

```bash
git clone https://github.com/abhinandan998/Phoenix-In-Warranty-Flow-Project.git
cd Phoenix-In-Warranty-Flow-Project
```

#### 2️⃣ Install Newman

```bash
npm install -g newman
```

#### 3️⃣ Install Newman HTML Extra Reporter

```bash
npm install -g newman-reporter-htmlextra
```

#### 4️⃣ Verify Installation

```bash
newman --version
```

### ▶️ Running the Tests

Execute the test suite using the Newman CLI:

```bash
newman run 'In-Warranty Flow Collection.postman_collection.json' \
  -e QA.postman_environment.json \
  -d testData.csv \
  -r cli,htmlextra \
  --reporter-htmlextra-export ./newman/index.html
```

#### Command Breakdown:

- `newman run` - Executes the Postman collection
- `-e` - Specifies the environment file
- `-d` - Provides test data from CSV file
- `-r` - Defines reporters (CLI and HTML Extra)
- `--reporter-htmlextra-export` - Sets the output path for HTML report

---

## 🔄 CI/CD Integration

This project supports multiple CI/CD platforms, providing flexibility and redundancy for automated testing.

---

## 🐙 GitHub Actions Workflow

GitHub Actions provides cloud-based automated testing with zero infrastructure management.

### Trigger Events

- 🔄 **Push to Main Branch** - Automatic execution on code changes
- 🖱️ **Manual Trigger** - Use `workflow_dispatch` for on-demand runs
- ⏰ **Scheduled Runs** - Cron-based execution at specified times

### Workflow Features

1. **Automated Testing** - Runs on Ubuntu VM with Newman
2. **Report Generation** - Creates beautiful HTML reports
3. **Artifact Upload** - Stores reports for team download
4. **GitHub Pages Deployment** - Publishes reports to live URL
5. **Email Notifications** - Sends results to team members via Gmail SMTP

### Sample Cron Schedule

```yaml
# Run tests every day at 9 AM UTC
schedule:
  - cron: '0 9 * * *'
```

---

## 🚀 Jenkins Pipeline

Jenkins provides powerful parallel execution capabilities with master-agent architecture on AWS EC2 instances.

### 🏗️ Infrastructure Setup

#### EC2 Master Server
- **Role**: Jenkins Controller
- **Responsibilities**:
  - Orchestrate pipeline execution
  - Schedule cron jobs
  - Aggregate reports from agents
  - Send email notifications

#### EC2 Agent Server (postman-agent)
- **Role**: Test Execution Node
- **Responsibilities**:
  - Execute test collections in parallel
  - Generate individual reports
  - Report back to master

### ⚡ Parallel Execution Strategy

The Jenkins pipeline runs **multiple collections simultaneously** for faster results:

```groovy
stage('Execute API Tests in Parallel') {
    parallel {
        stage('Collection 1') {
            agent any  // Runs on any available agent
            // Execute collection and generate report
        }
        stage('Collection 2') {
            agent { label 'postman-agent' }  // Runs on specific EC2 agent
            // Execute collection and generate report
        }
    }
}
```

### 🔄 Pipeline Stages

#### 1️⃣ **Parallel Execution Stage**

**Collection 1 (Any Agent):**
- Checkout code from GitHub
- Install Node.js v24 and Newman
- Execute `In-Warranty Flow Collection`
- Generate `Collection1_Report.html`
- Stash report for later merging

**Collection 2 (Postman Agent):**
- Checkout code from GitHub
- Install Node.js v24 and Newman
- Execute `In-Warranty Flow Collection`
- Generate `Collection2_Report.html`
- Stash report for later merging

#### 2️⃣ **Report Collection Stage**
- Unstash reports from both executions
- Merge all artifacts
- Archive reports for download

#### 3️⃣ **Notification Stage**
- Send email with test results
- Attach all HTML reports
- Include build status and links

### 📧 Email Notification Template

```
Subject: Jenkins Build #${BUILD_NUMBER} - Newman API Report

Hi Team,

API Automation execution completed.

Job: ${JOB_NAME}
Build: ${BUILD_NUMBER}
Status: ${currentBuild.currentResult}
Build URL: ${BUILD_URL}

Newman HTML reports are attached.

Thanks,
Abhinandan Basu
```

### ⏰ Scheduled Jenkins Jobs

Configure cron triggers in Jenkins:

```groovy
// Run every day at 9 AM
triggers {
    cron('0 9 * * *')
}

// Run every 6 hours
triggers {
    cron('0 */6 * * *')
}

// Run Monday to Friday at 8 AM
triggers {
    cron('0 8 * * 1-5')
}
```

### 🔐 Jenkins Credentials

Store sensitive data in Jenkins Credentials:

1. **GitHub Credentials** (`2892e60f-57ff-4e09-914f-4db3f621bff1`)
   - Type: Username with password
   - Usage: Repository checkout

2. **Email Configuration**
   - Gmail SMTP settings
   - App-specific password

### 📊 Build Status Handling

The pipeline intelligently handles test failures:

```groovy
if (status != 0) {
    echo "Collection FAILED"
    currentBuild.result = 'UNSTABLE'  // Mark as unstable, not failed
} else {
    echo "Collection PASSED"
}
```

**Build Results:**
- ✅ **SUCCESS**: All tests passed
- ⚠️ **UNSTABLE**: Some tests failed (still sends reports)
- ❌ **FAILURE**: Pipeline execution failed

### 🚀 Running Jenkins Pipeline

#### Prerequisites
1. Jenkins server installed on EC2 Master
2. Jenkins agent configured on EC2 Agent
3. Node.js 24 tool configured in Jenkins
4. Required plugins: Pipeline, Email Extension, NodeJS

#### Setup Steps

1. **Create New Pipeline Job**
   ```
   New Item → Pipeline → Enter name → OK
   ```

2. **Configure Pipeline**
   - Definition: Pipeline script from SCM
   - SCM: Git
   - Repository URL: `https://github.com/abhinandan998/Phoenix-In-Warranty-Flow-Project.git`
   - Branch: `main`
   - Script Path: `Jenkinsfile`

3. **Configure Build Triggers**
   - ✅ GitHub hook trigger for GITScm polling
   - ✅ Build periodically (add cron schedule)

4. **Save and Build**

---

## 🆚 Platform Comparison

| Feature | GitHub Actions | Jenkins |
|---------|---------------|---------|
| **Infrastructure** | Cloud-based, fully managed | Self-hosted on EC2 |
| **Setup Complexity** | Simple, minimal configuration | Requires server setup |
| **Parallel Execution** | Limited by plan | Unlimited with agents |
| **Cost** | Free tier available | EC2 + bandwidth costs |
| **Control** | Limited customization | Full control |
| **Best For** | Quick setup, public repos | Enterprise, complex workflows |

---

## 📊 Viewing Reports

### 🌐 Live GitHub Pages Report

Access the latest test execution report anytime:

**🔗 [View Live Report](https://abhinandan998.github.io/Phoenix-In-Warranty-Flow-Project/)**

### 📦 Downloading Archived Reports

1. Navigate to the **Actions** tab in the repository
2. Select the completed workflow run
3. Download the report from the **Artifacts** section

### 📧 Email Reports

Team members receive automated email notifications with:
- ✅ Test execution summary
- 📊 Pass/Fail statistics
- 🔗 Link to detailed HTML report

---

## 📸 Sample Report

<div align="center">

![Postman Report](https://raw.githubusercontent.com/abhinandan998/Phoenix-In-Warranty-Flow-Project/static-content/newman%20report.png)

*Example of the HTML report generated by newman-reporter-htmlextra*

</div>

---

## 🔧 Configuration

### GitHub Actions Environment Variables

The project uses the following environment variables (stored in GitHub Secrets):

- `GMAIL_USER` - Gmail account for sending reports
- `GMAIL_PASSWORD` - App-specific password for Gmail SMTP
- `RECIPIENT_EMAIL` - Email addresses for report recipients
- Custom API tokens and credentials (as required)

#### Setting Up GitHub Secrets

1. Go to your repository **Settings**
2. Navigate to **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Add your secrets with appropriate names and values

---

### Jenkins Configuration

#### 1️⃣ EC2 Master Server Setup

**Install Jenkins:**
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install Java
sudo apt install openjdk-17-jdk -y

# Add Jenkins repository
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

# Install Jenkins
sudo apt update
sudo apt install jenkins -y

# Start Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

**Configure Jenkins:**
1. Access Jenkins at `http://<EC2-PUBLIC-IP>:8080`
2. Get initial admin password: `sudo cat /var/lib/jenkins/secrets/initialAdminPassword`
3. Install suggested plugins
4. Create admin user

#### 2️⃣ EC2 Agent Server Setup

**Install Java and Node.js:**
```bash
# Install Java
sudo apt install openjdk-17-jdk -y

# Install Node.js v24
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
sudo apt install -y nodejs

# Verify installations
java -version
node -v
npm -v
```

**Connect Agent to Master:**
1. In Jenkins Master: **Manage Jenkins** → **Manage Nodes** → **New Node**
2. Node name: `postman-agent`
3. Type: **Permanent Agent**
4. Configure:
   - Remote root directory: `/home/ubuntu/jenkins`
   - Labels: `postman-agent`
   - Launch method: Launch agents via SSH
   - Host: EC2 Agent Private IP
   - Credentials: Add SSH credentials

#### 3️⃣ Install Jenkins Plugins

**Required Plugins:**
- Pipeline
- Git
- GitHub Integration
- Email Extension Plugin
- NodeJS Plugin
- Workspace Cleanup

**Installation Steps:**
1. **Manage Jenkins** → **Manage Plugins**
2. Go to **Available** tab
3. Search and install required plugins
4. Restart Jenkins

#### 4️⃣ Configure Node.js Tool

1. **Manage Jenkins** → **Global Tool Configuration**
2. Scroll to **NodeJS**
3. Click **Add NodeJS**
4. Name: `Nodejs 24`
5. Version: Select NodeJS 24.x
6. Save configuration

#### 5️⃣ Configure Email Notifications

1. **Manage Jenkins** → **Configure System**
2. Scroll to **Extended E-mail Notification**
3. Configure:
   - **SMTP server**: `smtp.gmail.com`
   - **SMTP port**: `465`
   - **Use SSL**: ✅ Checked
   - **Credentials**: Add Gmail credentials
4. Test configuration by sending test email

#### 6️⃣ Add GitHub Credentials

1. **Manage Jenkins** → **Manage Credentials**
2. Select **(global)** domain
3. Click **Add Credentials**
4. Configure:
   - Kind: Username with password
   - Scope: Global
   - Username: Your GitHub username
   - Password: GitHub Personal Access Token
   - ID: `2892e60f-57ff-4e09-914f-4db3f621bff1`
5. Save

#### 7️⃣ Security Group Configuration

**EC2 Master Security Group:**
- Allow inbound TCP 8080 (Jenkins UI)
- Allow inbound TCP 22 (SSH)
- Allow outbound all traffic

**EC2 Agent Security Group:**
- Allow inbound TCP 22 from Master's Security Group
- Allow outbound all traffic

---

## 👨‍💻 About the Author

<div align="center">

### Abhinandan Basu

**QA Automation Engineer | API & UI Testing Specialist**

</div>

Hi! I'm Abhinandan Basu, a passionate QA professional with **1.5+ years of experience** in automation and manual testing.

#### 🎯 Skillset

- **API Testing**: Postman, Rest Assured, Newman
- **UI Automation**: Selenium WebDriver
- **CI/CD**: GitHub Actions, Jenkins, AWS EC2
- **Languages**: Java, JavaScript, Groovy
- **Tools**: Git, AWS, Docker, Linux
- **DevOps**: Master-Agent Architecture, Parallel Execution, Cron Scheduling

#### 📫 Connect With Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abhinandan-basu/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/abhinandan998)

---


<div align="center">

### ⭐ Star this repository if you find it helpful!

**Made with ❤️ by Abhinandan Basu**

</div>
