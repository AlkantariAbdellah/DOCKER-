# DOCKER-Build-node-example-app-&&-run


A lightweight Docker-based setup for building and running your project easily. Clone this repo and get started in seconds!

---

## Overview

This repository contains:

- A Dockerfile to **build a containerized app** based on Node.js
- Preconfigured scripts to **build, run, and manage** the Docker container

---

## 🔧 Prerequisites

Make sure you have:

- [Docker](https://docs.docker.com/get-docker/) installed and running  the engine .

---

## ⚠️ Getting Started

### 1. Clone the Repository


   > git clone https://github.com/AlkantariAbdellah/DOCKER-.git
   > cd DOCKER-
### 2. Build the Docker Image


  > docker build -t my-node-app .
This builds the image named my-node-app using the Dockerfile in this repo.

### 3. Run the Container


  > docker run -d -p 3000:3000 my-node-app
  -d runs in detached mode (background)

  -p 3000:3000 maps port 3000 of the container to your local port 3000

   Your app should now be accessible at http://localhost:3000


   ###  Dockerfile 

   FROM node     _____  ( The base image would be node  ) 
    
   WORKDIR /app     ____   (  Working directory of the container , all the copy , run , cmd commands run on it   )
    
   COPY package.json /app    ____    (  Copy the package.json file on the working directory ) Optimization of dockerfile Image layers 
    
   RUN npm install   ____      (  Execute the command npm install if necessary , Installs the dependencies listed in package.json inside the container environment  )
    
   COPY . /app   ____     (  Copy all the content of the working directory "the code"  into /app the container )
    
   EXPOSE 80    ____     (  Expose the internal  port of the container to the port 80 'HTTP' , means the container listens on that port ) # Optional #

   CMD ["node","server.js"]   ____      (  Launch the app when the container starts  )

🛠️ Common Docker Commands

Build an image :

   > docker build -t Name-wanted .    [ -t tag ]

Run a container based on that image :

   > docker run --rm -p 80:80 Name_of_the_image  [ --rm remove the container when it's stopped , -p use the port 80 on the localhost to display the app env on the browser ]

List images:

   > docker images
   
List running containers:

   > docker ps

List all containers (even those not utilized):

   > docker ps -a
   
Stop a running container:

   > docker stop <container_id>

Remove a container:

   > docker rm <container_id>
Remove an image:
 
   > docker rmi my-node-app

Remove all unutilized containers :

   > docker container prune

Remove all unutilized  images :

   >  docker images prune 
