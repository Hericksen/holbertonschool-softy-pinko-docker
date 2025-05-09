# Utiliser la dernière image Ubuntu
FROM ubuntu:latest

# Mettre à jour APT et installer Python3 et pip3
RUN apt-get update && apt-get upgrade -y \
    && apt-get install -y python3 python3-pip \
    && rm -rf /var/lib/apt/lists/*

# Résoudre l'erreur de "EXTERNALLY-MANAGED"
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED || true

# Installer Flask et Flask-CORS
RUN pip3 install --no-cache-dir flask flask-cors

# Définir le répertoire de travail
WORKDIR /app

# Copier le fichier api.py dans le conteneur
COPY ./api.py /app/api.py

# Exposer le port 5252
EXPOSE 5252

# Définir la commande par défaut pour lancer le serveur Flask
CMD ["python3", "api.py"]
