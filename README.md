# TP DevOps Correction Docker

Correction de la partie Docker du module DevOps. Amusez-vous bien avec GitHub Actions !


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
