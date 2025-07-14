# docker
# 📘 Leçon Docker – Introduction et Commandes de Base

## 🚀 Qu'est-ce que Docker ?

Docker est une plateforme permettant de **créer**, **déployer** et **exécuter** des applications dans des **conteneurs**.

Un conteneur est une version légère d'une machine virtuelle, qui regroupe une application avec toutes ses dépendances, ce qui garantit que le code s'exécutera de la même manière partout.

---

## 🧱 Avantages de Docker

- Isolation des applications
- Légèreté des conteneurs
- Déploiement rapide
- Portabilité entre environnements
- Meilleure gestion des dépendances

---

## 🛠️ Commandes Docker de base

### 📦 1. Images et Conteneurs

```bash
# Télécharger une image depuis Docker Hub
docker pull <nom_de_l_image>

# Lister les images disponibles
docker images

# Supprimer une image
docker rmi <image_id>
```

---

### 🧰 2. Gestion des conteneurs

```bash
# Exécuter un conteneur
docker run <options> <nom_image>

# Exemple : exécuter nginx sur le port 8080
docker run -d -p 8080:80 nginx

# Lister les conteneurs actifs
docker ps

# Lister tous les conteneurs (même arrêtés)
docker ps -a

# Stopper un conteneur
docker stop <container_id>

# Supprimer un conteneur
docker rm <container_id>
```

---

### 📁 3. Volumes (données persistantes)

```bash
# Créer un volume
docker volume create mon_volume

# Lister les volumes
docker volume ls

# Supprimer un volume
docker volume rm mon_volume
```

---

### 🛠️ 4. Dockerfile (automatiser la création d'image)

Un fichier `Dockerfile` permet de définir une image personnalisée :

```Dockerfile
# Exemple simple
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]
```

Construire l'image :

```bash
docker build -t mon_app .
```

---

## 📦 Docker Compose

`docker-compose.yml` permet de gérer plusieurs services ensemble (ex. : app + base de données)

Exemple :

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: exemple
```

Lancer les services :

```bash
docker-compose up -d
```

---

## 🔎 Vérification et nettoyage

```bash
# Vérifier l'espace utilisé
docker system df

# Nettoyer les ressources inutilisées
docker system prune
```

---

## 📚 Ressources utiles

- [Docker Documentation](https://docs.docker.com/)
- [DockerHub](https://hub.docker.com/)
- [Play with Docker](https://labs.play-with-docker.com/)

---

*Créé par Mialy RANDRIAMIALINTSOA – Leçon Docker simplifiée pour les débutants.*
