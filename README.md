# 🐳 Europe-Travel-Website ✨
Hey there, fellow coders and cloud enthusiasts! 👋

Welcome to my little corner of the GitHub universe where Docker images meet the magic of Google Kubernetes Engine (GKE)! This project showcases a responsive tour & travel agency website built with HTML, CSS, and JavaScript, all packaged into a neat Docker container and deployed on a GKE cluster. It's all about creating an awesome travel experience—from code to cloud! ☁️💻


# What's the Buzz? 🐝
This repository contains all the essential ingredients for building, deploying, and running the Europe-Travel-Website on GKE. Think of it as a recipe for cloud-powered travel adventures! You'll find:

The website’s HTML, CSS, and JavaScript files
A Dockerfile to containerize the app
Kubernetes configuration files (YAML goodness!)
Handy scripts to build, push, and deploy the project


## Project Structure 📂
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


Getting Started 🚀
Ready to embark on this coding adventure? Follow these steps to get the project up and running:


Clone the Repo:

git clone https://github.com/your-username/your-repository.git
cd your-repository


Build the Docker Image:

./scripts/build.sh


Push to a Container Registry:

(This could be Artifact Registry, Docker Hub, etc.)

./scripts/push.sh


Deploy to GKE:

./scripts/deploy.sh



The Website Itself 🌐
This website is designed to be responsive, adapting beautifully to different screen sizes—from desktops to mobile devices. It's built using standard web technologies:

HTML: Provides the structure and content.
CSS: Styles the site to be visually appealing.
JavaScript: Adds interactivity and dynamic features.


Challenges and Triumphs (aka Bugs and Features) 🐛✨
Every journey has its bumps, and this project is no exception! I’ve faced some interesting challenges along the way (which you might notice in the code 😅), but I've also learned tons about Docker, Kubernetes, and cloud deployment. Stay tuned for more updates and improvements! 🔧📈


Contributing 🤗
Contributions are always welcome! If you spot something that could be improved (and trust me, there's always room for improvement!), feel free to open an issue or submit a pull request. Let's make this project even better together! 💪

## License 📜

[Choose a license - MIT, Apache 2.0, etc.]

Happy coding and safe travels! 🌍✈️

## Authors 🎉

[Wilber Gutiérrez, Rocío Vásquez, Verónica Guzmán, Evelyn Villeda, Dixi Figueroa].

---
