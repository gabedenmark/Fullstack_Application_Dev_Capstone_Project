<center>
    <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/IDSNlogo.png" width="400" alt="cognitiveclass.ai logo">
</center>

# Dealerships Review Portal - Fullstack Application Development Capstone Project
by **Gabe Denmark**

## Overview

This project is the final capstone for the **IBM Fullstack Software Developer Professional Certificate** course. The goal of this project is to develop a web application for a national car dealership with branches across the United States that allows users to view dealership information and leave reviews for each branch. The project uses a variety of technologies including **HTML**, **CSS**, **Javascript**, **React**, **Node.js**, **Python**, **Django**, **MongoDB**, **Docker** and **IBM Cloud**.


<h2>Table of Contents</h2>
<div class="alert alert-block alert-info" style="margin-top: 20px">
    <ul>
         <li>
            <a href="#PJ">Project Background</a>
        </li>
         <li>
            <a href="#KF">Key Features</a>
        </li>
          <li>
            <a href="#TU">Technologies Used</a>
        </li>
        <li>
            <a href="#ARCH">Architecture</a>
            <ul>
                <li><a href="#DW">Dealerships Website (Django)</a></li>
                <li><a href="#DRS">Dealerships and Reviews Service (Node.js/Express)</a></li>
                <li><a href="#SA">Sentiment Analyzer (IBM Cloud Code Engine)</a></li>
                <li><a href="#DB">Database</a></li>
                <li><a href="#keys">Database</a></li>
            </ul>
        </li>
        <li>
            <a href="#US">User Stories</a>
            <ul>
                <li><a href="#AU">Anonymous Users</a></li>
                <li><a href="#AUTHU">Authorized Users</a></li>
                <li><a href="#ADMU">Admin Users</a></li>
            </ul>
        </li>
        <li>
            <a href="#II">Installation Instructions</a>
            <ul>
                <li><a href="#CR">Clone the repository</a></li>
                <li><a href="#SBME">Set up the Backend Mongo Express Server</a></li>
                <li><a href="#SVE">Set up Virtual Enviroment</a></li>
                <li><a href="#SDB">Set up Django Backend</a></li>
                <li><a href="#FE">Frontend</a></li>
                <li><a href="#CE">Code Engine</a></li>
            </ul>
        </li>
        <li>
            <a href="#CICD">CI / CD</a>
        </li>
        <li>
            <a href="#DPL">Deployment</a>
        </li>
        <li>
            <a href="#CN">Contributors</a>
        </li>
    </ul>

</div>

<hr>

<a id="PJ"></a>
### Project Background

A market survey conducted by the car dealership company revealed a strong interest from customers in a centralized platform where they could view reviews of dealerships nationwide. The goal is to provide transparency and increase customer trust in the dealership network by enabling users to read reviews and submit their own.

<a id="KF"></a>
### Key Features

- **Anonymous Users**: View dealership details and reviews.
- **Authorized Users**: Log in, submit reviews, and view reviews for each dealership.
- **Admin Users**: Manage dealership information, including adding car makes, models, and other attributes.
- **Sentiment Analysis**: Analyze the sentiment of customer reviews using an IBM Cloud-based sentiment analyzer service.

<a id="TU"></a>
## Technologies Used

- **HTML**: Markup language Front-end development for the site.
- **CSS**: Used to specify the presentation and style of the site.
- **Javascript**: Programming language that allows the implementation of complex front-end features in the site.
- **React**: Frontend framework for building dynamic user interfaces.
- **Node.js**: Server to handle dealership and review data with MongoDB.
- **Python**: Backend programming language used for structured, object-oriented and functional programming on the site.
- **Django**: Backend web framework of Python ecosystem to manage dealership data, user authentication.
- **MongoDB**: Database used to store dealership and review data.
- **Docker**: Containerization technology for packaging the application and services.
- **IBM Cloud Code Engine**: Cloud platform to deploy the sentiment analysis service.
- **CI/CD**: Continuous Integration and Continuous Deployment pipeline for efficient code management and delivery.

<a id="ARCH"></a>
## Architecture

The architecture consists of the following components:

<a id="DW"></a>
**Dealerships Website (Django)**:
   - Microservices for managing dealerships, car models, reviews, and user authentication.
   - Interaction with a MongoDB database through a proxy service.

<a id="DRS"></a>
**Dealerships and Reviews Service (Node.js/Express)**:
   - Microservice to handle CRUD operations for dealers and reviews.
   - Hosted in a Docker container for easy deployment.

<a id="SA"></a>
**Sentiment Analyzer (IBM Cloud Code Engine)**:
   - Analyzes the sentiment of review text (positive, negative, or neutral).

<a id="DB"></a>
**Database**:
   - **SQLite** for storing car make and model data in Django.
   - **MongoDB** for storing dealer and review data in the Node.js service.

<a id="US"></a>
## User Stories

<a id="AU"></a>
### Anonymous Users
- View the **Contact Us** and **About Us** pages.
- View a list of dealerships across the United States, with the ability to filter by state.
- View reviews for each dealership.

<a id="AUTHU"></a>
### Authorized Users
 In addition to anonymous features, authorized users can:
- Submit reviews for any dealership.
- Submit a review which will appear at the top of the list of reviews on the dealership detail page.

<a id="ADMU"></a>
### Admin Users
- Log into the admin interface to manage dealership data.
- Add new makes, models, and other attributes for dealerships.

<a id="II"></a>
## Installation Instructions

<a id="CR"></a>
1. **Clone the repository**:
  ```bash
  git clone https://github.com/gabedenmark/Fullstack_Application_Dev_Capstone_Project.git
  cd Fullstack_Application_Dev_Capstone_Project
  ```

<a id="SBME"></a>
2. **Set up the Backend Mongo Express Server**
   - Navigate to the Database directory
   ```bash
   cd Fullstack_Application_Dev_Capstone_Project/server/database
   ```
   - Build the nodeapp:
   ```bash
   docker build . -t nodeapp
   ```
   - Start the server:
   ```bash
   docker-compose up
   ```
   - The server will be running on port 3030.
   - Get the URL and add it to the .env file, that is located in the djangoapp folder (no / backslashes).
   - Make sure there is a space between backend_url and = in your .env file.

    ```bash
   backend_url =your backend url(server)
   sentiment_analyzer_url =your code engine deployment url/
   ```

<a id="SVE"></a>
3. **Set up Virtual Environment**
   - Open new terminal:
   ```bash
   cd Fullstack_Application_Dev_Capstone_Project/server
   pip install virtualenv
   virtualenv djangoenv
   source djangoenv/bin/activate
   ```

<a id="SDB"></a>
4. **Set up Django Backend**
   - Install Python dependencies :
   ```bash
   python3 -m pip install -U -r requirements.txt 
   ```
   - Run migrations to set up the database and start development server:
   ```bash
   python3 manage.py makemigrations
   python3 manage.py migrate
   python3 manage.py runserver
   ```

<a id="FE"></a>
5. **Frontend (React):**
   - Open new terminal, navigate to the frontend directory and install dependencies:
   ```bash
   cd Fullstack_Application_Dev_Capstone_Project/serverserver/frontend
   npm install
   ```
   - Run the React app:
   ```bash
   npm run build
   ```

<a id="CE"></a>
6. **Code Engine**:
   To run the Cloud Code Engine service to access Sentiment Analyzer Microservice:
   - Navigate to Skills Network Toolbox, and under Cloud, find Code Engine.
   - Start code engine by creating a project.
   - Once the code engine set up is complete, you can see that it is active. Click on Code Engine CLI to begin the pre-configured CLI in the terminal below.
   - You will observe that the pre-configured CLI statrup and the home directory is set to the current directory.
   - As a part of the pre-configuration, the project has been set up and Kubeconfig is set up. The details that are shown on the terminal.
   - Navigate in the same terminal run the following commands:
   
   ```bash
   cd Fullstack_Application_Dev_Capstone_Project/server/djangoapp/microservices
   ```
   - Run the following command to docker build the sentiment analyzer app(note the code engine instance is transient and is attached to your lab space username):
   ```bash
   docker build . -t us.icr.io/${SN_ICR_NAMESPACE}/senti_analyzer
   ```
   - Push the docker image by running the following command:
   ```bash
   docker push us.icr.io/${SN_ICR_NAMESPACE}/senti_analyzer
   ```
   - Deploy the senti_analyzer application on code engine:
   ```bash
   ibmcloud ce application create --name sentianalyzer --image us.icr.io/${SN_ICR_NAMESPACE}/senti_analyzer --registry-secret icr-secret --port 5000
   ```
   - Obtain the URL and add to .env file, which is inside the folder djangoapp (you must add / backslash)
   - Make sure there is a space between sentiment_analyzer_url and = in your .env file.
   ```bash
   backend_url =your backend url
   sentiment_analyzer_url =your code engine deployment url/
   ```

<a id="CICD"></a>
## CI / CD
- Workflow is created to lint files to meet PEP8 guidelines. When code is pushed to the repository, the workflow will automatically begin to lint the Python and JavaScript files.

<a id="DPL"></a>
## Deployment 
1. Kubernetes: Deploy the application and its microservices on Kubernetes for scalability.
2. IBM Cloud: Deploy the Sentiment Analyzer microservice on IBM Cloud Code Engine.

<a id="CN"></a>
### Contributors: 
- Upkar Lidder - Lead Full-Stack Software Developer
- Lavanya - Full-Stack Developer
- Yan Luo - Backend Developer
- Priya - Frontend Developer
- **Sierra Ripoche - Full-Stack Developer**


#Troubleshooting

Please ensure that you stop and restart the entire Django server whenever you make any code changes using the following commands:

python3 manage.py makemigrations  

python3 manage.py migrate --run-syncdb  

python3 manage.py runserver  

Additionally, stop and restart the backend server to reflect the changes using these commands:  

docker build . -t nodeapp  

docker-compose up  
