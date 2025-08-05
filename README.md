# Procédure d'installation d'un environnement PHP avec XAMPP et Composer

Cette procédure vous permettra de mettre en place un environnement de développement local avec les outils suivant :
- XAMPP (Apache + MariaDB + PHP + Perl) qui intègre notamment un serveur HTTP de développement ;
- composer qui est le gestionnaire de dépendance des projets PHP

L'objectif 

## Étape 1 : Installation de XAMPP

1. **Télécharger XAMPP**
   - Rendez-vous sur le site officiel de [XAMPP](https://www.apachefriends.org/index.html).
   - Téléchargez la version appropriée pour votre système d'exploitation.

2. **Installer XAMPP**
   - Suivez les instructions d'installation par défaut.
   - Assurez-vous d'inclure les composants Apache, MySQL, PHP et phpMyAdmin.

3. **Lancer XAMPP**
   - Ouvrez le panneau de contrôle XAMPP.
   - Démarrez les services Apache et MySQL.

## Étape 2 : Paramétrage des variables d'environnement

Les **variables d'environnement** sont essentielles dans un système d'exploitation pour stocker des configurations accessibles par les applications.

Dans notre cas nous allons les utiliser pour pouvoir accéder aux logiciels de l'application depuis un **terminal** (Powershell par exemple).

Ceci est fait afin de pouvoir appeler `php` ou même `composer` depuis n'importe quel répertoire afin de pouvoir gérer et développer nos projets.

1. **Ajouter PHP aux variables d'environnement**
   - Suivez la procédure indiquée par [cet article](https://iut-info.univ-reims.fr/users/cutrona/intranet/installation-configuration/php-windows/index.html#configuration-de-windows-pour-utiliser-php-en-ligne-de-commande).
   - **Attention de bien ajouter le chemin vers le dossier `php` de votre installation XAMPP** (par exemple, `C:\xampp\php`).

2. **Vérifier l'installation de PHP**
   - Ouvrez une nouvelle fenêtre de terminal ou d'invite de commandes.
   - Tapez la commande suivante pour vérifier que PHP est correctement installé :
     ```sh
     php --version
     ```

## Étape 3 : Installation de Composer

### Qu'est-ce que composer ?

Composer est un outil de **gestion de dépendances pour PHP**.

Il permet de :
- **Gérer les dépendances** : Composer peut télécharger et installer automatiquement les bibliothèques dont le projet a besoin.
- **Faciliter la mise à jour** : simplification de la mise à jour des bibliothèques.
- **Autoloading** : Composer peut génèrer un fichier d'autoloading pour vos classes, ce qui vous évite d'avoir à inclure manuellement chaque fichier.

### Procédure d'installation

1. **Télécharger et installer Composer**
   - Rendez-vous sur le site officiel de [Composer](https://getcomposer.org/download/).
   - Lancez l'installateur et installer l'outil **pour tous les utilisateurs**

2. **Modification de la variable d'environnement PATH**
   - Tout comme PHP il vous faut ajouter le dossier contenant les exécutables de `composer` dans le `PATH`
   - Répétez l'opération comme pour PHP en ajoutant le bon chemin (par exemple `C:\ProgramData\ComposerSetup\bin` pour une installation par défaut)

3. **Vérifier l'installation de Composer**
   - Ouvrez une nouvelle fenêtre de terminal.
   - Tapez la commande suivante pour vérifier que Composer est correctement installé :
     ```sh
     composer --version
     ```

## Étape 5 : Initialisation d'un projet avec Composer

1. **Créer un nouveau projet**
   - Ouvrez une nouvelle fenêtre de terminal.
   - Naviguez jusqu'au dossier de votre projet (par exemple, `C:\xampp\htdocs\mon_projet`).
   - Tapez la commande suivante pour initialiser un nouveau projet Composer :
     ```sh
     composer init
     ```
   - Suivez les instructions pour configurer votre projet.

2. **Installer des dépendances**
   - Pour ajouter une dépendance à votre projet, utilisez la commande suivante :
     ```sh
     composer require nom_du_paquet
     ```
   - Par exemple, pour installer le paquet `monolog/monolog`, tapez :
     ```sh
     composer require monolog/monolog
     ```