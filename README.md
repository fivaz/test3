# Installation et Configuration

## Prérequis 
### Composer
* https://getcomposer.org/download/
* PHP et Mysql (évidemment)

### Paquets natifs de PHP
Laravel utilise quelques paquets de PHP qui ne sont pas activés automatiquement quand tu installes PHP, donc il faut les activer. 
il faut aller où t'as installé PHP (probablement *C:/php/*) et chercher le fichier **php.ini**.

dans le fichier il faut décommenter les lignes :
```bash 
extension=fileinfo
```
```bash 
extension=pdo_mysql
```

## Fichiers manquant

Une fois clonée l'application depuis le Github, elle ne marchera pas parce que certains fichiers n'ont pas été *pushés* pour 
une question de "bonnes pratiques".

ils sont:

#### .env
Un fichier qui continent les informations pour se connecter à la base de donné.

Pour avoir le fichier **.env** il faut simplement copier le fichier **.env.example** et renommez la copie comme .env 
(si windows ne te laisse pas renommer un fichier sans un nom, que avec une extension, fait ça sur phpstorm)

Dans le fichier .env dans ce paragraphe il faut changer les informations si elles ne correspondent pas à ta base de données
```bash 
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=arene
DB_USERNAME=root
DB_PASSWORD=
```
#### vendor/
Pour avoir le fichier vendor dans ta machine il suffit de taper sur la console, dans la racine du projet (cd c:/chemin/vers/le/projet pour y accéder depuis le terminal)
```bash 
composer install
```
Cela va télécharger tous les libraries utilisées par laravel (ce n'est pas moi qui les as ajoutées)

## Base de données
### Tables
vous avez besoin de créer une base de données appelée : **arene**.
Il ne faut pas ajouter des tables dans cette base de données Laravel fera ça tout seul, il faut juste taper :
```bash 
php artisan migrate
```
### Données
Pour ajouter les données aux tables il faut taper :
```bash 
php artisan db:seed
```

## Comment faire marcher Laravel ?
il suffit d'exécuter
```bash 
php artisan serve
```
Laravel sera servi dans la porte 8000, donc *localhost:8000*, cependant c'est juste l'api des produits qui a été faite pour l'instant donc il faut aller sur :

```bash 
localhost:8000/api/products
```
Cette page devra montrer une liste avec toutes les données existant dans la table products de la base de données. Si tu les vois, tu as bien configuré Laravel.

## Aide

Lis attentivement la documentation de Laravel, elle est probablement une des documentations les plus faciles
https://laravel.com/docs/8.x

Pour comprendre ce que j'ai fait il suffit de regarder ce tutoriel, tout ce que j'ai fait va jusqu'à la minute 30:10
https://www.youtube.com/watch?v=mgdMeXkviy8
