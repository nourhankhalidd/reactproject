React Application Deployment with Docker & AWS Elastic Beanstalk


This project demonstrates a React application built with Docker and deployed on AWS Elastic Beanstalk using a complete CI/CD pipeline powered by GitHub Actions.



🧩 Project Overview

The main goal of this project is to automate the process of building, testing, and deploying a React app.
It uses:
Docker for containerization
Docker Compose for local development
GitHub Actions for Continuous Integration (CI)
AWS Elastic Beanstalk for Continuous Deployment (CD)



⚙️ Technologies Used
| Tool                      | Purpose                 |
| ------------------------- | ----------------------- |
| **React.js**              | Frontend framework      |
| **Node.js**               | Runtime environment     |
| **Docker**                | Containerization        |
| **Docker Compose**        | Local development setup |
| **GitHub Actions**        | CI/CD automation        |
| **AWS Elastic Beanstalk** | Deployment and hosting  |




🧱 Project Structure
├── Dockerfile
├── Dockerfile.dev
├── docker-compose-dev.yml
├── src/
├── public/
├── package.json
├── .github/
│   └── workflows/
│       └── deploy.yml
└── README.md



🐳 Local Development
You can run the app locally using Docker Compose with hot-reload enabled.

docker compose -f docker-compose-dev.yml up

The app will be available at:
👉 http://localhost:4000

To stop the containers:

docker compose down



🔁 CI/CD Workflow
1. Continuous Integration (GitHub Actions)
Whenever a commit is pushed to the master branch:
The app is built inside a Docker container
Automated tests are executed
A Docker image is generated
2. Continuous Deployment (AWS Elastic Beanstalk)
Once the build succeeds:
The latest Docker image is deployed automatically to Elastic Beanstalk
The environment URL updates to reflect the latest version

Example environment URL:
🌍 http://react.us-east-1.elasticbeanstalk.com/



🧪 Testing
Tests are executed automatically via the test service in Docker Compose:

docker compose -f docker-compose-dev.yml run test




🛡️ Environment Variables

Make sure to configure the following secrets in your GitHub repository:
| Variable                | Description                          |
| ----------------------- | ------------------------------------ |
| `DOCKER_USERNAME`       | Docker Hub username                  |
| `DOCKER_PASSWORD`       | Docker Hub access token or password  |
| `AWS_ACCESS_KEY_ID`     | AWS access key for Elastic Beanstalk |
| `AWS_SECRET_ACCESS_KEY` | AWS secret access key                |





📦 Deployment

To manually deploy:
Build the Docker image:
docker build -t your-app-name .
Push to Docker Hub:
docker push your-app-name
Deploy the image through AWS Elastic Beanstalk or via GitHub Actions.





🧠 Key Features

Full CI/CD automation
Zero-downtime deployment
Easy local development using volumes
Scalable AWS hosting environment
Test automation integration




Author
Nourhan Khalid
www.linkedin.com/in/nourhan-khalid-22n







