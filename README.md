## Git Version Control for a Cloud Project
By: Kris Stallard

## Purpose
Demonstrates how Git and GitHub can be used to manage a cloud project, as well as understanding how to successfully run and create a Docker container from a Docker image.

## Files Included
- README.md
- index.html
- Dockerfile

## How does version control help?
Version control is a fundamental part of cloud projects as it gives the ability for students or developers to collaborate by tracking changes and being able to manage different versions of their work. 

## Docker Reflection Questions

### What is Docker?
Docker is a program that enables virtualization to create lightweight packages with no full operating system like a VM, called containers. These containers are used to run software, and are used very frequently in modern development.

### What is a Docker image?
A template/blueprint that is created through the instructions of a Dockerfile. This will then have everything that a Docker container needs to run itself.

### What is a Docker container?
An actual runnable instance of a Docker image. It uses the template of a Docker image to run itself as a self-contained application.

### How to build and run an application using Docker?
1. Install Docker Desktop & run it 
2. Create a Dockerfile (no .txt or any other file extension) and add instructions inside such as what image, files, and port.
3. Build the Docker image using the first command listed below and verify with docker images
4. Run the actual container using the second command listed below and verify with docker ps

## Docker Commands 
1. docker build -t cloud-service-demo:1.0 .
2. docker run -d --name cloud-demo-container -p 8080:80 cloud-service-demo:1.0