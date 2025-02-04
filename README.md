📌 Projet Flask avec Docker Swarm

🏗 Introduction

Ce projet est une application Flask conteneurisée et orchestrée avec Docker Swarm. Elle inclut un serveur Flask, une base de données PostgreSQL et un proxy Nginx.

✅ Prérequis

Docker & Docker Compose installés

Un compte Docker Hub (si besoin de push des images)

Accès à Internet pour récupérer les images Docker

🚀 Installation

Cloner le projet :

git clone https://github.com/flaskProject.git
cd flaskProject

Se connecter à Docker Hub (si besoin) :

docker login

Construire et pousser l'image Flask :

docker build -t votre-utilisateur/flask-app:latest .
docker push votre-utilisateur/flask-app:latest

Déployer la stack Docker Swarm :

docker stack deploy -c docker-stack.yml myapp

🛠 Utilisation

Accéder à l'application Flask : http://localhost

Accéder à Portainer : http://localhost:9000

⚙️ Architecture Docker

├── flask-app (Python Flask)
├── db (PostgreSQL)
├── nginx (Proxy)
└── portainer (Monitoring)

🔄 Commandes utiles

Voir les services : docker service ls

Voir les logs : docker service logs -f myapp_flask-app

Supprimer la stack : docker stack rm myapp

🏥 Healthchecks

Flask : Route /health

PostgreSQL : pg_isready

🛑 Dépannage

Erreur "image reference must be provided" → Assurez-vous que l'image Flask est bien push sur Docker Hub.

Service qui ne démarre pas → docker service ps myapp_flask-app pour voir les erreurs.

Accès refusé → Vérifiez les logs avec docker logs <container_id>


