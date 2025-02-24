<center>
    <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/IDSNlogo.png" width="400" alt="cognitiveclass.ai logo">
</center>

# Dealerships Review Portal - Fullstack Software Developer Capstone Project
by **Gabe Denmark**

## Overview

This project is the final capstone for the **Fullstack Software Developer** certification course. The goal of this project is to develop a web application for a national car dealership with branches across the United States, enabling users to view dealership information and leave reviews for each branch. This project leverages various technologies including **Django**, **React**, **Node.js**, **MongoDB**, **Docker**, and **IBM Cloud**.


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
            <a href="#quiz">Quiz on Dictionaries</a>
        </li>
        <li> 
            <a href="#Scenario">Scenario</a>
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

- **Django**: Backend web framework to manage dealership data, user authentication, and reviews.
- **React**: Frontend framework for building dynamic user interfaces.
- **Node.js**: Server to handle dealership and review data with MongoDB.
- **MongoDB**: Database used to store dealership and review data.
- **Docker**: Containerization technology for packaging the application and services.
- **IBM Cloud Code Engine**: Cloud platform to deploy the sentiment analysis service.
- **CI/CD**: Continuous Integration and Continuous Deployment pipeline for efficient code management and delivery.

<a id="ARCH"></a>
## Architecture

The solution architecture consists of the following components:

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

