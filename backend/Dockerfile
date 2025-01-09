# Utiliser une image Python officielle
FROM python:3.13-slim

# Définir le répertoire de travail dans le conteneur
WORKDIR /app

# Copier les dépendances
COPY requirements.txt .

# Installer les dépendances
RUN pip install --no-cache-dir -r requirements.txt

# Copier le code du projet dans le conteneur
COPY sig_backend/ ./sig_backend/

# Copier les fichiers d'environnement (optionnel, selon le besoin)
COPY .env ./

# Exposer le port sur lequel Django écoutera
EXPOSE 8000

# Commande par défaut pour démarrer le serveur Django
CMD ["python", "sig_backend/manage.py", "runserver", "0.0.0.0:8000"]
