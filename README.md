
# Deploy a NodeJS Server Using Kubernetes
Hello, today we will figure out how Kubernetes works using the example of a small web server on NodeJS. \
This small case will help you familiarize yourself with the concept of clustering in k8s.


# In this tutorial we'll cover:
1. Building the application image
2. Pushing the image to Docker Hub Registry
3. Deploying the application in Kubernetes

###### Environment:
[Docker-Descktop](https://www.docker.com/products/docker-desktop) with enable Kubernetes at settings. You can still use [Minikube](https://kubernetes.io/ru/docs/tasks/tools/install-minikube/).

#### 1/3 Building the application image

`$ cd ./src` \
`$ docker build -t myapp:v1 .`


#### 2/3 Pushing the image to Docker Hub Registry
Sign in DockerHub \
`docker login` \
`$ docker push myapp:v1`


#### 3/3 Deploying the application in Kubernetes








[Learn Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
