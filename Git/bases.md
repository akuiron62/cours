# GIT
C’est un outil qui permet de faire du versioning.
Le versioning permet d’avoir un historique de toutes les modifications que l’on fait à un projet.
Nous avons une sorte de timeline qui permet de voir toutes les modifications et de pouvoir revenir en arrière à tous moments.
Git permet également de résoudre les problèmes de conflits. C’est utile lorsque l’on travaille à plusieurs sur le même projet.
Git permet de faire des ‹ des branches › : Créer une branche, c’est en quelque sorte comme créer une “copie” de votre projet pour développer et tester de nouvelles fonctionnalités sans impacter le projet de base.

***

## Pourquoi Git ?
C’est un système décentralisé, c’est à dire que chaque utilisateur va avoir un historique du projet. L’utilisateur travail en local et lorsqu’il est satisfait il envoi les modifications sur le serveur distant. Git est donc plus rapide et plus sécurisé (car les données sont dupliquées) que les systèmes centralisés.

***

## Installer Git

Se rendre sur l’adresse : [git-scm.com](git-scm.com)

Pour Windows :
* télécharger l’installeur (cliquer sur installer pour windows)
* executer l’installeur
* cliquer sur next deux fois
* choisissez le répertoire d’installation et cliquez sur next
* décochez Additional icons et si vous utilisez git en ligne de commande vous pouvez décocher également windows explorer intégration, cliquez ensuite sur next deux fois
* la dernière option est à privilégiée (Use git and optionnal Unix tools from the window command prompt) car en plus de git elle installe également des commandes unix telles que find et sort. Cliquez sur Next
* Configuring the line ending conversions permet de choisir l’option pour gérer les sauts de lignes (les sauts de lignes entre windows et unix sont différents). Laissez l’option par défaut. Cliquez sur Next
* Et enfin cliquez sur Finish
* Git et maintenant accessible dans l’invite de commande windows (windows + R et taper cmd ou powershell)
* Tapez ensuite : `git help`qui permet de voir l’ensemble des commandes git disponibles.

Pour Mac :
* télécharger l’installeur (cliquer sur installer pour mac)
* executer le logiciel d’installation
* cliquez sur continuer puis sur installer
* Entrez le mot de passe administrateur du mac puis cliquez sur installer le logiciel
* Pour vérifier l’installation : ouvrir le terminal et tapez `git help`

Pour Linux :
* tapez la commande : `sudo apt-get install git`
* pour vérifier l’installation : `git --help`

## Commandes Git

* Initialiser Git dans le dossier à versionner : `git init`

* Configurer Git avant de pouvoir l’utiliser :
    * `git config --global user.email "contact@akuiron.com"`
    * `git config --global user.name "akuiron"`
    * `git config --list` → permet de voir la configuration de git

* Voir l’état de notre dossier : `git status`

* Ajouter un fichier à la zone de staging : `git add nomDuFichier`ou `git add --all`pour ajouter tous les fichiers ou `git add ‘’*.html’’`ajoute tous les fichiers html

* Commiter un projet : `git commit -m ‘’ajout du fichier readme.md’’`

* Pour ignorer des fichiers : 
    * créer un fichier .gitignore 
    * ajouter les noms des fichiers à ignorer ou ajouter par exemple `*.tmp`pour ignorer tous les fichiers avec l’extension tmp ou `tmp/*`pour ignorer tous les fichiers contenus dans le dossier tmp.

* Voir l’historique de tout ce qui a été fait : 
    * `git log`
    * `git log -n 2`on n’affiche que les deux derniers commits avec leur ID qui est une clef SHA1
    * `git log -p nomDuFichier`affiche les commits pour le fichier nommé
    * `git diff`prend tous les fichiers modifiés depuis le dernier commit et nous montre les modifications
