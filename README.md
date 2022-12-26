## A simple web application deployed to Kubernetes via helm

### Snapshots:

1. Starting the app, clone https://github.com/NickyAsaph/my-devops-test);

Installations:
Docker desktop
Node => v14
Minikube
Kubectl
Helm

  + This application contains the frontend (app) and the backend (userservice) microservices built with Node.js 
  + The app (frontend) service basically fetches the sentence **This page is rendered from the App** from the backend service using an Application Programming Interface (API) call to the backend service to fetch data.

  ##  Flow of execution
  + You start up the frontend and backend services in the root directory and run

        npm run start:all
  + You can access the app (frontend) service by accessing it on port 5000 on the browser by running 

        http://localhost:3000

    + That will then fetch the word **"This page is rendered from the App"**from the server service through API.
  
  + We can access our userservice service on the browser by entering:

        http://localhost:4000
 
 + The nginx serves as the loadbalancer service that allows traffic into the cluster we would create on minikube for the applications

 + The nginx, app and userservice applications are dockerized and built then helm chart is used to deploy them into the minikube cluster.

 + Lastly we configure an ingress controller to allow traffic to access the loadbalancer service and thereby access the applications.