
# Deploy a NodeJS Server Using Kubernetes

[![contributions](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat-square)](https://github.com/svishnevskii/deploy-kubernetes-nodejs-server/issues)

Hello, today we will figure out how Kubernetes works using the example of a small web server on NodeJS. \
This small case will help you familiarize yourself with the concept of clustering in k8s.


## In this tutorial, we'll cover:
1. Building the application image
2. Pushing the image to Docker Hub Registry
3. Deploying the application in Kubernetes

> Environment:
[Docker-Descktop](https://www.docker.com/products/docker-desktop) with enable Kubernetes at settings. You can still use [Minikube](https://kubernetes.io/ru/docs/tasks/tools/install-minikube/).

***

## 1/3 Building the application image

`$ cd ./src` \
`docker build -t svishnevskii/myapp:v1 .`

>replace `svishnevskii` with your USERNAME from DockerHab

After a successful build, you can find the image in the list by calling the `docker images` command

## 2/3 Pushing the image to Docker Hub Registry
Sign in DockerHub \
`docker login` \
> Input your personal access, after you'll see `Login Succeeded`

`docker push myapp:v1`


## 3/3 Deploying the application in Kubernetes
`$ cd ./kube`

##### Creating a Deployment
A Deployment provides declarative updates for Pods and ReplicaSets. \
> Create the Deployment by running the following command: \
`kubectl apply -f deployment.yaml`

Run `kubectl get deployments` to check if the Deployment was created

##### Creating a Service
In Kubernetes, a Service is an abstraction which defines a logical set of Pods and a policy by which to access them (sometimes this pattern is called a micro-service). The set of Pods targeted by a Service is usually determined by a selector.

> Create the Service: \
`kubectl apply -f service.yaml`

Run `kubectl get svc` to check.

##### Creating a Ingress
Ingress exposes HTTP and HTTPS routes from outside the cluster to services within the cluster. Traffic routing is controlled by rules defined on the Ingress resource.

> Create the Ingress: \
`kubectl apply -f ingress.yaml`

Run `kubectl get ing` to check.

If created Ingress doesn't have value on the `Address` field then you should set up Nginx Ingress Controller, for the Minikube environment just run `minikube addons enable ingress` command and check.


### Results
Docker-Descktop:
Check URL http://localhost/

> Minikube: Get external IP on your Minikube 'minikube ip' and use his.

## Bug Reports and Improvements
If you experience any bugs or see anything that can be improved or added, please feel free to [open an issue](https://github.com/svishnevskii/deploy-kubernetes-nodejs-server/issues) here or simply contact me through any of the methods below. Thanks in advance!
