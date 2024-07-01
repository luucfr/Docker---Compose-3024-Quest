# Docker-Compose-3024-Quest

## Prérequis

- Docker
- Docker Compose

## Structure du projet

```
my-wordpress-app/
├── docker-compose.yml
├── wordpress/
│   ├── Dockerfile
│   └── wp-content/
├── mysql/
│   ├── Dockerfile
├── secrets/
│   ├── db_password.txt
│   ├── db_root_password.txt
├── .env
└── README.md
```

## Configuration

### Fichier .env

Le fichier `.env` contient les variables d'environnement non sensibles :

```
WORDPRESS_DB_NAME=wordpress
WORDPRESS_DB_USER=wordpress
WORDPRESS_DB_HOST=db:3306
```

### Docker Secrets

Les fichiers secrets sont stockés dans le dossier `secrets` :

- `secrets/db_password.txt` : Contient le mot de passe de la base de données WordPress.
- `secrets/db_root_password.txt` : Contient le mot de passe root de MySQL.

Assurez-vous que ces fichiers existent et contiennent les mots de passe appropriés avant de lancer les conteneurs Docker.

## Utilisation

1. Clonez ce dépôt :

    ```
    git clone https://github.com/luucfr/Docker-Compose-3024-Quest
    cd Docker-Compose-3024-Quest
    ```

2. Créez les fichiers secrets dans le dossier `secrets` :

    ```
    mkdir -p secrets
    echo "your_db_password" > secrets/db_password.txt
    echo "your_db_root_password" > secrets/db_root_password.txt
    ```

3. Assurez-vous que le fichier `.env` est configuré correctement :

    ```
    # .env
    WORDPRESS_DB_NAME=wordpress
    WORDPRESS_DB_USER=wordpress
    WORDPRESS_DB_HOST=db:3306
    ```

4. Démarrez les conteneurs Docker :

    ```
    docker-compose up -d
    ```

5. Accédez à l'application WordPress via `http://localhost:8000`.

## Gestion des mots de passe sensibles

Les mots de passe sensibles ne doivent pas être stockés directement dans les fichiers de configuration. Utilisez Docker Secrets pour une gestion sécurisée des mots de passe.

Les fichiers secrets utilisés dans ce projet sont :
- `secrets/db_password.txt` : Contient le mot de passe de la base de données WordPress.
- `secrets/db_root_password.txt` : Contient le mot de passe root de MySQL.

Assurez-vous que ces fichiers sont créés et contiennent les valeurs appropriées avant de lancer les conteneurs Docker.
