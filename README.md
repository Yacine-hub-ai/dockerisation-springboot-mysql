# Dockerisation d'une Application Spring Boot avec MySQL

##  Description
Conteneurisation complète d'une application **Java Spring Boot** avec une base de données **MySQL**, orchestrée via **Docker Compose**. Le projet couvre la création des Dockerfiles, la configuration du réseau Docker, la gestion des volumes persistants et le déploiement multi-conteneurs.

## Objectifs
- Conteneuriser une application Spring Boot
- Mettre en place une base de données MySQL dans un conteneur
- Orchestrer les services avec Docker Compose
- Gérer la persistance des données avec des volumes Docker

##  Technologies utilisées
| Technologie | Rôle |
|---|---|
| Docker | Conteneurisation |
| Docker Compose | Orchestration multi-conteneurs |
| Spring Boot | Framework applicatif Java |
| MySQL | Base de données relationnelle |
| Maven | Gestion des dépendances Java |
| Docker Hub | Registry d'images |

##  Architecture
```
┌─────────────────────────────────────────┐
│           Docker Compose                │
│  ┌──────────────────┐  ┌─────────────┐ │
│  │   app_container  │  │ bd_container│ │
│  │  (Spring Boot)   │──│  (MySQL)    │ │
│  │   Port: 8080     │  │  Port: 3306 │ │
│  └──────────────────┘  └─────────────┘ │
│          │                    │         │
│          └────────────────────┘         │
│              docker_network             │
│                    │                    │
│              Volume MySQL               │
└─────────────────────────────────────────┘
```

##  Structure du projet
```
project/
├── app/
│   ├── Dockerfile
│   ├── src/
│   └── pom.xml
├── docker-compose.yml
└── README.md
```

##  Déploiement
```bash
# Cloner le projet
git clone https://github.com/votre-username/dockerisation-springboot-mysql.git

# Lancer les conteneurs
docker-compose up -d

# Vérifier les conteneurs
docker ps

# Accéder à l'application
http://localhost:8080
```

##  Configuration Docker Compose
- Réseau bridge dédié entre les conteneurs
- Volume persistant pour les données MySQL
- Variables d'environnement pour la configuration de la BDD
- Healthcheck sur le conteneur MySQL avant démarrage de l'app

##  Contexte académique
Projet — Master 2 Réseaux et Télécommunications (RETEL), UCAD — 2026

