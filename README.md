# Nginx Deployment on Minikube

This repository contains the configuration files and instructions for deploying an Nginx web server on Minikube. The setup includes a ConfigMap to manage the index.html file and a Kubernetes Service to expose the Nginx deployment.

## Prerequisites

- minikube
- kubectl

## Files

- index.html - The HTML file served by the Nginx server.
- nginx-deployment.yaml - Kubernetes Deployment configuration for Nginx.
- nginx-service.yaml - Kubernetes Service configuration to expose Nginx.

## Steps to Setup

1. Create the ConfigMap

To manage the index.html file within Kubernetes, create a ConfigMap using the below command: 

  kubectl create configmap nginx-config --from-file=index.html

2. Deploy the configurations

  kubectl apply -f nginx-deployment.yaml
  kubectl apply -f nginx-service.yaml

3. Access the service using below command, This command will open a browser window with the URL where Nginx service is accessible. We can see the content of the index.html file served by Nginx.

  minikube service nginx-service
