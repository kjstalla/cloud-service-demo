## Cloud Computing Lab Assignments - Git, Docker, Kubernetes
By: Kris Stallard

## Purpose
Demonstrates how Git and GitHub can be used to manage a cloud project, how to successfully run and create a Docker container from a Docker image, and uses Kubernetes to deploy and scale the application.

## Files Included
- README.md
- index.html
- Dockerfile
- kubernetes/deployment.yaml
- kubernetes/service.yaml

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

## Kubernetes README questions

### What is Kubernetes?

Kubernetes is a container orchestration platform that is used to deploy, manage, and scale containerized applications.

### Pods, Deployments, and Services

1. Pod: The smallest deployable unit in Kubernetes, containing at least one or more containers.
2. Deployment: Manages Pods and ensures that the desired number of application instances are running.
3. Service: Provides a stable way to access the application Pods.

### How to start Minikube and make the Docker image available?
You can start a local Kubernetes cluster using Docker with:

```bash
minikube start --driver=docker
```

A docker image can be loaded into the minikube using:

```bash
minikube image load cloud-service-demo:1.0
```

### How to apply the Deployment and Service YAML files?:

```bash
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
```

### How to access the application using kubectl port-forward?

Use this command to access the application through the web browser.

```bash
kubectl port-forward service/cloud-service-demo 8080:80
```

The port number can be changed if needed. 
For this example, view the site at localhost:8080 in the web browser.

