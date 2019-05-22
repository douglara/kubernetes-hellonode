# Hellonode

This is a first interactions with Kubernetes nodes and pod using minikube

## Getting started

First create a Docker image run: 
  $ docker build -t hello-node:v1 .

Second create a Pod:
  $ kubectl create -f kubernetes-pod.yml

Show Pods:
  $ kubectl get pods

Create Kubernetes Deployment to runs a health check on of your Pod
  $ kubectl run hellonode --image=hello-node:v1 --port=8080 --image-pull-policy=Never

Expose service
  $ kubectl expose deployment hellonode --type=NodePort

Show URL
  $ minikube service hello-node