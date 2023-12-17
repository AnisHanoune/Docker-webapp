# Docker-webapp
![image](https://github.com/ahanoune/Docker-webapp/assets/119413702/89c4d855-4949-4c0e-bd8b-7416b2b86a2b)

Ce dépôt est une application simple pour répertorier les étudiants avec un serveur Web (PHP) et une API (Flask)


** Objectifs :
améliorer un processus de déploiement d'application existant
versionner la version de l'infrastructure
aborder les meilleures pratiques lors de la mise en œuvre de l'infrastructure Docker
**

**Infrastructure :

Machine virtuelle sur Centos7.6 
** 

** Application


student_list comporte deux modules :

le premier module est une API REST (avec authentification de base requise) qui envoie la liste de souhaits de l'étudiant basée sur un fichier JSON
Le deuxième module est une application web écrite en HTML + PHP qui permet à l'utilisateur final d'obtenir une liste d'étudiants.

Il est maintenant temps de vous expliquer le rôle de chaque fichier :

Construire et tester 

Image de base
"python:2.7-buster"

L'API utilise le moteur FLASK. Installations  des packages nécessaire 

Créez un dossier de données "/data" à la  "/" où les données seront stockées et les déclarer sous forme de volume

** 


** Infrastructure en tant que code


Le fichier docker-compose.yml va déployer deux services :

site Web : l'interface utilisateur final 
         - image : php:apache
         - Communication entre les conteneurs site-web et API 
API : l'image créée auparavant

Registre Docker 
 déployier un registre privé et stockier les images construites
 
- Déploiement d'un docker registre "Image : registry"
- une interface Web pour voir l'image poussée en tant que conteneur "Image: joxit/docker-registry-ui"
**



