# Restaurant Management Application

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Clone the Repository](#clone-the-repository)
  - [Start Docker Services](#start-docker-services)
  - [Access the Application](#access-the-application)
- [API Endpoints](#api-endpoints)
- [Jenkins CI/CD Setup](#jenkins-cicd-setup)
- [Screenshots](#screenshots)
- [License](#license)

---

## Introduction
This is a **Restaurant Management Application** built using the MERN stack (MongoDB, Express, React, Node.js). The application allows users to view restaurant menus, ratings, and additional details. The backend API is integrated with MongoDB, and the application is containerized using Docker for easy deployment.

## Features
- View a list of restaurants.
- View menus and prices for each restaurant.
- Seed the database with initial restaurant data.
- Containerized application using Docker Compose.
- CI/CD setup using Jenkins.

## Technologies Used
- **Frontend**: React.js
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Containerization**: Docker
- **Continuous Integration**: Jenkins

## Project Structure
```
restaurant-app
├── client               # Frontend application
│   ├── public
│   └── src
├── server               # Backend application
│   ├── models           # Mongoose models
│   └── routes           # API routes
├── docker-compose.yml   # Docker Compose configuration
└── README.md            # Project documentation
```

## Prerequisites
Before starting, ensure you have the following installed on your system:
- [Docker](https://www.docker.com/)
- [Node.js](https://nodejs.org/)
- [Git](https://git-scm.com/)

## Getting Started

### Clone the Repository
```bash
git clone https://github.com/Yassin238/RESTAURENT-APP.git
cd restaurant-app
```

### Start Docker Services
1. Build and start the containers:
   ```bash
   sudo docker-compose up --build
   ```
2. Verify that the containers are running:
   ```bash
   docker ps
   ```

### Access the Application
- **Frontend**: Open your browser and go to `http://localhost:3000`
- **Backend API**: Access `http://localhost:5000/restaurants`

## API Endpoints
| HTTP Method | Endpoint           | Description               |
|-------------|--------------------|---------------------------|
| GET         | `/restaurants`     | Get a list of restaurants |

## Jenkins CI/CD Setup
### Jenkins Configuration
1. **Run Jenkins Docker Container**:
   ```bash
   docker run -d -p 8080:8080 -p 50000:50000 --name jenkins --privileged -v jenkins_home:/var/jenkins_home salahgo/jenkins:dind
   ```
2. **Access Jenkins**:
   Go to `http://localhost:8080`.
3. **Install Plugins**:
   - Docker
   - NodeJS
4. **Add Credentials**:
   - Go to **Manage Jenkins > Credentials > Global Credentials**
   - Add your DockerHub and GitHub credentials.
5. **Create a New Pipeline**:
   - Add the repository URL.
   - Use a Jenkinsfile for build steps.

## Screenshots
_Add screenshots of the application here._

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
