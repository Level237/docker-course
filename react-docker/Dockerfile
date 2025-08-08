FROM node:20-alpine

# Créer utilisateur
RUN addgroup app && adduser -S -G app app

WORKDIR /app

# Copier package.json et package-lock.json
COPY package*.json ./

# Installer dépendances
RUN npm install

# Copier le reste du code
COPY . .

# Donner les droits à l'utilisateur
RUN chown -R app:app /app

USER app

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host"]