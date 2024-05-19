# Utiliser l'image de base contenant Node.js
FROM node:14 AS build

# Définir le répertoire de travail dans le conteneur
WORKDIR /app

# Copier les fichiers package.json et package-lock.json
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier les fichiers source de l'application
COPY . .

# Construire l'application Angular en mode production
RUN npm run build --prod

# Utiliser un serveur web léger pour servir l'application Angular
FROM nginx:alpine

# Copier les fichiers de construction de l'application Angular dans le répertoire de travail du serveur web
COPY --from=build /app/dist/* /usr/share/nginx/html/

# Exposer le port 80 pour que l'application soit accessible
EXPOSE 80

# Commande pour démarrer le serveur web NGINX
CMD ["nginx", "-g", "daemon off;"]

