# LMS4-4-Using-Containers-for-Deployment

Containerization is a critical skill for DevOps engineers because in the last 5 years there has been a shift in the way software is delivered and architected. 

## How it works

Travela has an `API` and a `web` application. Both applications are dployed to `GCP(Google Cloud Platform)` in containers.

The appliction is built using docker, into a docker image which is used for deployment. Docker is used to create an image which is then uploaded to `GCR(Google Container Registry)`. From here the deployment scripts utilize the said image to launch containers running the application used to build the image. This means that the application is running inside the container which is running inside a node/pod. The node/pod are aspects of `GKE(Google Kubernetes Engine)` which is the deployment orchestration tool of choice in Travela. 

The running container exposes specified port(s) to allow interaction/connection to the application running inside the container from outside the container. This is how the web application running in its own container is able to communicate to the api application running in another container.
