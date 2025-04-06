# Image de base
FROM node:18

# Installer bash (au cas où il manquerait)
RUN apt-get update && apt-get install -y bash

# Dossier de travail
WORKDIR /app

# Copier les fichiers package.json et package-lock.json
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste des fichiers
COPY . .

# Construire l'application
RUN npm run build

# Installer un serveur statique
RUN npm install -g serve

# Exposer le port
EXPOSE 4200

# Lancer l'application (serveur de développement)
CMD ["npm", "start"]