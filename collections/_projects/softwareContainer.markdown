---
title:  "Software Containerisation Project"
permalink: /projects/softcon-proj/
layout: page
---
## What is the Software Containerization Project?
This was the final project for the XM_0091-Software_Containerization course at Vrije Universiteit done during my master's degree. This project consists of a three-tier application (Backend, frontend, and database) which is then containerized and deployed using Docker and Kubernetes.

The app itself was a simple reminders web app where users can upload a reminder on a webpage and then retrieve these reminders at a later date. The app was kept as simple as possible as it was not the focus of the project, rather the focus was on containerizing and deploying it.

## How does it work?
The frontend UI was built using Vue, the backend API was built using Python (Flask) and the database was a MongoDB database. Each tier was containerized using Docker. Kubernetes was then used to allow these containers to communicate with each other, scale horizontally according to load, and communicate externally. The full Kubernetes deployment can be seen below. Kubernetes allows us to restrict how the containers communicate and handle containers going down, hence ensuring that the application is always available in the case of errors or updates. The final deployment was created on the Google Cloud environment.

![architecture](/images/architecture.jpeg)
*Image 1 showing the architecture of the kubernetes deployment*


## What did I learn?
Key takeaways include advanced Docker usage for creating and managing containers, Kubernetes for orchestration, deploying and scaling applications on the cloud, particularly GKE, and integrating different technology stacks (MongoDB, Flask, Vue.js) in a unified workflow.

For further details, the repository is available [here](https://github.com/dalviebenu/XM_0091-Software_Containerization){:target="_blank"}.