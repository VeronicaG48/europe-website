# 🐳 Europe-Travel-Website ✨
Hey there! 👋

Welcome to our GitHub repository! This project demonstrates the development and deployment of a responsive travel and tour agency website, built using HTML, CSS, and JavaScript. The website is containerized using Docker and deployed on a Google Kubernetes Engine (GKE) cluster, showcasing a seamless transition from local development to cloud deployment. This project exemplifies best practices in modern web development and cloud infrastructure, providing an efficient and scalable solution for showcasing travel experiences. ☁️💻


## What's the Buzz? 🐝
This repository contains all the essential components for building, deploying, and running the Europe-Travel-Website on GKE. Think of it as a recipe for cloud-powered travel adventures! You'll find:

The website’s HTML, CSS, and JavaScript files
A Dockerfile to containerize the app
Kubernetes configuration files (YAML goodness!)
Handy scripts to build, push, and deploy the project


## Project Structure 📂

```
Europe-Travel-Website/
├── Dockerfile              # The blueprint for the Docker image 🚀
├── kubernetes/             # Kubernetes config files for deployment
│   ├── deployment.yaml     # Defines how the website runs on GKE
│   ├── service.yaml        # Exposes the website to the world (or at least the cluster)
│   └── ... other YAML files ...
├── scripts/                # Helpful scripts for building, pushing, and deploying
│   ├── build.sh            # Builds the Docker image 🛠️
│   ├── push.sh             # Pushes the image to a container registry 📤
│   └── deploy.sh           # Deploys the app to GKE 🌐
└── website/                # The HTML, CSS, and JS files for the website
    ├── index.html          # The main page
    ├── css/                # Stylesheets
    │   └── style.css
    ├── js/                 # JavaScript files
    │   └── script.js
    └── ... other website files ...
```


## Getting Started Deployment steps 🚀
Let’s get started! Follow the steps below to set up and run the project:

### Clone the teaser website repository:
git clone https://github.com/GNiruthian/Europe-Travel-Website-html-css-js.git
cd Europe-Travel-Website-html-css-js

- IMPORTANT: Change the folder name to europe_travel


### Create a Dockerfile:

FROM nginx:alpine

COPY europe_travel /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]


### Build the Docker image:
docker build -t europe-website .


### Run Locally to Test:
docker run -p 8080:80 europe-website


### Push to Google Container/Artifact Registry:
Tag the image for Google Cloud:
docker tag europe-website gcr.io/linuxvmtest-442314/europe-website


### Authenticate Docker with Google Cloud:
gcloud auth configure-docker


### Push the image:
docker push gcr.io/linuxvmtest-442314/europe-website


### Create a GKE cluster to host the website:
gcloud container clusters create europe-website-cluster \
    --zone=us-central1-a \
    --machine-type=e2-micro \
    --num-nodes=3 \


### Get cluster's credentials
gcloud container clusters get-credentials europe-website-cluster --zone=us-central1-a


### Create a deployment.yaml file: use nano deployment.yaml

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: europe-website
spec:
  replicas: 3
  selector:
    matchLabels:
      app: europe-website
  template:
    metadata:
      labels:
        app: europe-website
    spec:
      containers:
      - name: europe-website
        image: gcr.io/linuxvmtest-442314/europe-website
        ports:
        - containerPort: 80 
```

### Create a service.yaml file: use nano service.yaml

```
apiVersion: v1
kind: Service
metadata:
  name: europe-website-service
spec:
  type: LoadBalancer
  selector:
    app: europe-website
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
```


### Apply the files:
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml


### Verify the Load Balancer:
* Get the external IP of the LoadBalancer:
kubectl get service europe-website-service


### Finalize and Publish GitHub Repository

* git init
* git add .
* git commit -m "Initial commit"
  
  - git config --global user.email "guzmanlaura@telsal.cloud"
   - git config --global user.name "veronica guzman"
* git remote add origin https://github.com/VeronicaG48/europe-website.git
* git push -u origin main 
make sure to have the correct access using token instead of password



## Challenges, Recommendations and Triumphs 🐛✨💡
- The folder name needs to be changed to "europe-travel" because cloud shell may not recognize folder names with spaces or capital letters.
- Change the docker file to the proper folder name.
  

## Contributing 🤗
If you spot something that could be improved, feel free to open an issue or submit a pull request 💪

## License 📜

[Choose a license - MIT, Apache 2.0, etc.]


## Authors 🎉

- Wilber Gutiérrez
- Rocío Vásquez
- Verónica Guzmán
- José Menéndez
- Evelyn Villeda
- Dixi Figueroa.

Happy coding and safe travels! 🌍✈️
---
