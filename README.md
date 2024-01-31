# Deploying Application to Kubernetes Cluster

This guide provides step-by-step instructions for deploying your application using Docker and Kubernetes.

### Prerequisites

Before you begin, ensure you have the following installed:

**Docker:** [Install Docker](https://docs.docker.com/get-docker/)

**Kubernetes:** [Install Kubernetes](https://kubernetes.io/docs/setup/)

**kubectl:** [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

**Docker Hub account:** [Sign up for Docker Hub](https://hub.docker.com/)

### Dockerizing Your Application

Follow these steps to package your application into a Docker container:

`Dockerfile:` Create a Dockerfile in the root directory of your application with the following content.

Dockerfile
```bash
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

![Alt text](image.png)


Build Image: Build your Docker image using the following command:

```bash
docker build -t your-dockerhub-username/your-image-name:tag .
```

Replace `your-dockerhub-username`, `your-image-name`, and `tag` with appropriate values.

### Pushing Image to Docker Hub

Follow these steps to push your Docker image to Docker Hub:

**Login to Docker Hub:** Log in to Docker Hub using the following command:

```bash
docker login
```
Enter your Docker Hub `username` and `password` when prompted.

**Tag Image:** Tag your Docker image with your Docker Hub username and repository name:

```bash
docker tag your-image-name your-dockerhub-username/your-image-name:tag
```
Replace `your-dockerhub-username`, `your-image-name`, and `tag` with appropriate values.

**Push Image:** Push your Docker image to Docker Hub:

```bash
docker push your-dockerhub-username/your-image-name:tag
```
Replace `your-dockerhub-username`, `your-image-name`, and `tag` with appropriate values.

### Deploying Application to Kubernetes

Apply the manifests using
```bash
kubectl apply -f deployment.yaml service.yaml
```

Once the deployment is successful, you can access your application using the IP for your application.

```bash
kubectl get svc
```
![Alt text](image-1.png)