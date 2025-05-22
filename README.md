# TP DevOps Correction Docker

📁 Structure du projet
Ce dépôt contient une API simple, un serveur HTTP avec page statique, une base de données PostgreSQL, ainsi qu’un système de déploiement automatisé via Ansible et GitHub Actions.

```
.
├── .github/workflows/       # Déploiement CI/CD (GitHub Actions)
├── database/                # Service PostgreSQL
├── http-server/             # Serveur HTTP affichant une page HTML
├── my-project/ansible/      # Fichiers Ansible pour déploiement distant
├── simple-api/              # API simple en Java
├── ssh/                     # Clé SSH pour Ansible (non versionnée)
├── docker-compose.yaml      # Orchestration globale des services
└── README.md                # Documentation du projet
```

📂 Détail des dossiers

🔁 .github/workflows/
Contient les workflows GitHub Actions, notamment deploy.yml pour :

Générer une clé SSH temporaire

Se connecter au serveur distant

Exécuter Ansible pour déployer automatiquement l’application

🐘 database/
Contient la configuration Docker pour une base PostgreSQL :

docker-compose.yml : définit le service PostgreSQL avec volume, utilisateur, mot de passe.

README.md : instructions spécifiques au service base de données.

🌐 http-server/
Ce dossier contient un serveur HTTP simple qui affiche une page HTML.

Peut être basé sur un serveur comme NGINX, Apache, ou un serveur maison.

Sert à exposer la page statique principale sur axelle.brosse.takima.cloud.

🤖 my-project/ansible/
Contient les scripts Ansible pour le déploiement :

inventories/setup.yml : liste des hôtes et variables (ex: ansible_user)

playbook.yml : définit les tâches à exécuter sur le serveur (copie des fichiers, docker-compose up, etc.)

🧩 simple-api/
API Java simple, probablement déployée en tant que microservice.

Contient le code source Java

Peut avoir son propre Dockerfile pour conteneurisation

🔐 ssh/
Dossier contenant les clés SSH utilisées pour la connexion Ansible.

⚠️ Ne pas versionner de clé privée dans ce dossier – les clés doivent être gérées via GitHub Secrets ou .gitignore.

🐳 docker-compose.yaml
Fichier principal d’orchestration. Il peut :

Lancer tous les services (API, serveur HTTP, PostgreSQL)

Être utilisé pour des tests en local avant déploiement

Commandes utiles :

`docker-compose up --build`


# 🚀 Déploiement avec Ansible
Le projet est conçu pour être déployé automatiquement sur un serveur distant (ex. axelle.brosse.takima.cloud) via Ansible et GitHub Actions.

# 📁 Dossiers Ansible typiques :
ansible/inventories/setup.yml : inventaire Ansible (liste des hôtes).

ansible/playbook.yml : liste des tâches à exécuter (installation Docker, lancement des containers...).

# ⚙️ CI/CD avec GitHub Actions
Un fichier deploy.yml dans .github/workflows/ permet de déclencher le déploiement à chaque push sur main, en :

Se connectant au serveur distant via SSH.

Transférant les fichiers.

Exécutant ansible-playbook.

# ✅ Prérequis
Java installé pour backend_api_basic

Docker & Docker Compose

Clé SSH privée dans les secrets GitHub (ID_RSA)

Serveur distant accessible (ex: axelle.brosse.takima.cloud)
