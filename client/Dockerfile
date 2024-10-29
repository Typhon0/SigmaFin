# client/Dockerfile

# Utiliser l'image de base de Node.js 20
FROM node:20

# Définir le répertoire de travail dans le conteneur
WORKDIR /app

# Installer Bun
RUN curl -fsSL https://bun.sh/install | bash
ENV PATH="/root/.bun/bin:${PATH}"

# Copier les fichiers package.json et bun.lockb dans le conteneur
COPY package.json bun.lockb ./

# Installer les dépendances avec Bun
RUN bun install

# Copier le reste des fichiers de l'application dans le conteneur
COPY . .

# Exposer le port sur lequel l'application Svelte sera accessible
EXPOSE 3000

# Définir la commande pour démarrer l'application
CMD ["bun", "run", "dev"]
