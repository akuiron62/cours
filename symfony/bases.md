# Symfony [symfony.com](https://symfony.com/)

## Créer un projet :
* Projet avec tous les bundles (cas pour un site complet) : `    composer create-project symfony/website-skeleton my_project_name`
* Projet avec le minimum de bundles installés : `    composer create-project symfony/skeleton my_project_name`

* Run your application:
    1. Go to the project directory
    2. Create your code repository with the git init command
    3. Download the Symfony CLI at https://symfony.com/download to install a development web server

  * Read the documentation at https://symfony.com/doc

## Structure des dossiers
### bin : contient des executables qui permet d ›effectuer certaines opérations
* console
* phpUnit : pour effectuer des tests unitaires

### config : contient les fichiers de configuration de notre projet (routes.yml, services.yml)
####     packages : contient les fichiers liés à la configuration des différents packages

### public : ce dossier sera la racine de notre serveur web (il faudra donc faire pointer notre hebergement directement sur ce dossier)

### src : contient le code PHP de notre application (il correspond par défaut au namespace App, qui est spécifié directement dans le fichier composer.json)

### templates : contient les vues de nos applications au format TWIG (modèle M(odel) V(ue) C(ontroller))

### tests : contient les tests unitaires et les tests fonctionnels

### translations : contient les traductions pour le site (pour les sites multilangues)

### var : contient les caches et les logs (Vérifier que ce dossier a les droits en écritures afin que PHP puisse écrire dedans)

### vendor : dossier propre à composer

## fichier .env :
* APP_ENV : permet de spécifier l ›environnement (developpement ou production)
* APP_SECRET : sert au hashage de certaines informations
* DATABASE_URL : url vers notre base de donnée (remplacer les informations par défaut par vos propres informations)
* MAILER_URL : utilisé par swiftmailer permet d ›envoyer des mails

## Se mettre dans le dossier contenant le projet avec la commande : `cd my_project`

## Lancer le serveur : `php -S localhost:8000 -t public`

## La console (Située dans le dossier bin) : permet d › effectuer différentes opérations en lien avec le framework symfony
    `php bin/console`  --> affiche la liste de tous les arguments disponibles
    
    `php bin/console server:run` --> permet de lancer le serveur, remplace la commande php -S localhost:8000 -t public