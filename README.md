# 🚀 Postman API Automation Integration with GitHub Actions

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
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [GitHub Actions Workflow](#-github-actions-workflow)
- [Viewing Reports](#-viewing-reports)
- [Configuration](#-configuration)
- [About the Author](#-about-the-author)
- [Contributing](#-contributing)

---

## 🎯 Overview

This repository demonstrates a **Proof of Concept (POC)** for integrating Postman API tests with GitHub Actions. The project showcases automated API testing with comprehensive reporting, scheduled execution, and seamless CI/CD integration.

### 🌟 What Makes This Project Special?

- ✅ **Fully Automated**: Tests run automatically on every push to the main branch
- 📊 **Beautiful HTML Reports**: Generated with newman-reporter-htmlextra
- 📧 **Email Notifications**: Automated test reports sent via Gmail SMTP
- 🌐 **Live Report Viewing**: Reports published to GitHub Pages for easy access
- ⏰ **Scheduled Execution**: Cron-based automated test runs
- 🔒 **Secure**: Secrets management with GitHub Secrets
- 🎯 **Comprehensive Testing**: Happy flows, negative scenarios, and edge cases

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🔄 **CI/CD Integration** | Automated test execution on every push or manual trigger |
| 📈 **Detailed Reporting** | HTML reports with test results, assertions, and response times |
| 📧 **Email Notifications** | Automatic delivery of test reports to team members |
| 🌐 **GitHub Pages** | Live, always-accessible test reports |
| ⏱️ **Scheduled Runs** | Cron-based automated testing at specified intervals |
| 📦 **Artifact Storage** | Test reports archived for team download |
| 🔐 **Security First** | Environment variables and secrets properly managed |
| 🖥️ **Self-Hosted Runner** | AWS EC2 instance for enhanced control and performance |

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
<td align="center" width="25%">
<img src="https://www.vectorlogo.zone/logos/getpostman/getpostman-icon.svg" width="48" height="48" alt="Postman" />
<br><strong>Postman</strong>
<br><sub>API Testing</sub>
</td>
<td align="center" width="25%">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" width="48" height="48" alt="Node.js" />
<br><strong>Node.js v22</strong>
<br><sub>Runtime Environment</sub>
</td>
<td align="center" width="25%">
<img src="https://avatars.githubusercontent.com/u/7647292?s=200&v=4" width="48" height="48" alt="Newman" />
<br><strong>Newman</strong>
<br><sub>CLI Runner</sub>
</td>
<td align="center" width="25%">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/github/github-original.svg" width="48" height="48" alt="GitHub Actions" />
<br><strong>GitHub Actions</strong>
<br><sub>CI/CD Pipeline</sub>
</td>
</tr>
<tr>
<td align="center" width="25%">
<strong>newman-reporter-htmlextra</strong>
<br><sub>HTML Reporting</sub>
</td>
<td align="center" width="25%">
<strong>Gmail SMTP</strong>
<br><sub>Email Notifications</sub>
</td>
<td align="center" width="25%">
<strong>GitHub Pages</strong>
<br><sub>Report Hosting</sub>
</td>
<td align="center" width="25%">
<strong>AWS EC2</strong>
<br><sub>Self-Hosted Runner</sub>
</td>
</tr>
</table>

---

## 📁 Project Structure

```
Phoenix-In-Warranty-Flow-Project/
│
├── 📄 In-Warranty Flow Collection.postman_collection.json   # Postman collection with API tests
├── 🌍 QA.postman_environment.json                          # Environment variables and configurations
├── 📊 testData.csv                                         # Test data for data-driven testing
├── 📋 README.md                                            # Project documentation
├── ⚙️ .github/
│   └── workflows/                                          # GitHub Actions workflow files
└── 📂 newman/                                              # Generated test reports (auto-created)
    └── index.html                                          # HTML test report
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

## ⚙️ GitHub Actions Workflow

The project includes automated CI/CD workflows that trigger on:

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

### Environment Variables

The project uses the following environment variables (stored in GitHub Secrets):

- `GMAIL_USER` - Gmail account for sending reports
- `GMAIL_PASSWORD` - App-specific password for Gmail SMTP
- `RECIPIENT_EMAIL` - Email addresses for report recipients
- Custom API tokens and credentials (as required)

### Setting Up GitHub Secrets

1. Go to your repository **Settings**
2. Navigate to **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Add your secrets with appropriate names and values

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
- **CI/CD**: GitHub Actions, Jenkins
- **Languages**: Java, JavaScript
- **Tools**: Git, AWS, Docker

#### 📫 Connect With Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abhinandan-basu/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/abhinandan998)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

<div align="center">

### ⭐ Star this repository if you find it helpful!

**Made with ❤️ by Abhinandan Basu**

</div>
