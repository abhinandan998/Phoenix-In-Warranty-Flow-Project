# Postman API Automation Integration with Github Action #

This repository is a demostration for POC for integrating postman tests with github actions. The tests are written in Postman and they are executed on the VM with the help of newman and newman-reporter-htmlextra.
Github Actions will trigger the project execution on every push to the main branch. You can also execute the project manually using workflow_dispatch. The Project runs on a schedule time with the help of the cron job.

The HTML report is archieved and kept in the artifact section for the team to download it. Along with that they can view the report directly from the github page: https://abhinandan998.github.io/Phoenix-In-Warranty-Flow-Project/.
The latest report is mailed to the team members using GMAIL SMTP.

## About ME ##
Hi My Name is Abhinandan Basu. I have 1.5+ years of experience in Automation Testing and manual testing. My skillset includes UI Automation with selenium webdriver and for API testing I use Rest Assured and
you can connect me over: (https://www.linkedin.com/in/abhinandan-basu/)

## Testing Coverage ##
1. Happy Flow Testing
2. Negative Testing and Edge case Testing
3. Token Testing
4. Data driven Testing with csv
5. Schema validation
6. Secrets Management with github secrets


## Tech Stach ##
1. Postman
2. Node.js 22v
3. Newman
4. newman-reporter-htmlextra
5. Github Actions
6. Gmail SMTP
7. Github Pages
8. CSV for Data Drivern Testing
9. AWS-EC2 insatnce for self hosting github runner.

## GitHub Pages ##
You can directly view the latest test report of the postman Test at the github page link: https://abhinandan998.github.io/Phoenix-In-Warranty-Flow-Project/.

## HTML Report ##
The Report will be created in the newman folder
![Postman Report](https://raw.githubusercontent.com/abhinandan998/Phoenix-In-Warranty-Flow-Project/static-content/newman%20report.png)

## Project STructure ##

```
Phoenix Inwarenty flow
├─ In-Warranty Flow Collection.postman_collection.json    # Collection File
├─ QA.postman_environment.json   #Environment File
└─ testData.csv      #TestData file

```

## How to run the Project? ##
You can run the project on your local system for that:
1. Clone the project on the Local System: https://github.com/abhinandan998/Phoenix-In-Warranty-Flow-Project.git
2. Install Nodejs and npm from https://nodejs.org/en
3. Install Newman using ``` npm install -g newman ```
4. Install Newman-reporter-htmlextra using ``` npm install -g newman-reporter-htmlextra ```
5. Run the Newman command : |
```
        newman run 'In-Warranty Flow Collection.postman_collection.json' \
             -e QA.postman_environment.json \
             -d testData.csv \
             -r cli,htmlextra \
             --reporter-htmlextra-export ./newman/index.html

```




