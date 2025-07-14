# Django Docker App

Une application Django containerisée avec Docker, configurée pour les environnements de développement et de production.

## 🛠 Prérequis

Avant de commencer, assurez-vous d'avoir installé :

- [Docker](https://docs.docker.com/get-docker/) (version 20.10+)
- [Docker Compose](https://docs.docker.com/compose/install/) (version 2.0+)

## 🚀 Installation

1. **Clonez le repository**
   ```bash
   git clone https://github.com/Athe03/djangoDocker.git
   cd djangoDocker
   ```

2. **Naviguez vers le répertoire de l'application**
   ```bash
   cd my_docker_django_app
   ```

3. **Créez le fichier d'environnement**
   ```bash
   cp .env.sample .env
   ```

## 🎯 Utilisation

### Environnement de développement

1. **Construire et lancer l'application**
   ```bash
   docker-compose -f docker-compose.dev.yml up --build
   ```

2. **Accéder à l'application**
   Ouvrez votre navigateur à l'adresse : http://localhost:8000

3. **Arrêter l'application**
   ```bash
   docker-compose -f docker-compose.dev.yml down
   ```

### Environnement de production

1. **Construire et lancer l'application**
   ```bash
   docker-compose -f docker-compose.prod.yml up --build -d
   ```

2. **Vérifier le statut**
   ```bash
   docker-compose -f docker-compose.prod.yml ps
   ```

## ⚙️ Configuration des environnements

### Développement (.env.dev)
```env
DEBUG=1
SECRET_KEY=your-secret-key-here
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]
```

### Production (.env.prod)
```env
DEBUG=0
SECRET_KEY=your-production-secret-key
DJANGO_ALLOWED_HOSTS=your-domain.com
```