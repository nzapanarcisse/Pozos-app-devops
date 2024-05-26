# architecture application

![project](https://user-images.githubusercontent.com/18481009/84582395-ba230b00-adeb-11ea-9453-22ed1be7e268.jpg)


------------

# Projet Docker - Application POZOS

## Contexte
L'entreprise POZOS m'a confié la tâche de conteneuriser leur application web et API afin de faciliter le déploiement et la maintenance de l'infrastructure.

## Objectifs
- Construire l'image Docker de l'API POZOS en respectant les spécifications fournies
- Créer un fichier docker-compose.yml pour déployer l'application complète
- Mettre en place un registre Docker privé pour stocker les images

## Étapes du projet

### 1. Construction de l'image Docker de l'API
- Utilisation de l'image de base "python:2.7-buster"
- Spécification du mainteneur de l'image
- Copie du code source de l'API dans le conteneur à la racine
- Installation des dépendances Flask, Flask-HTTPAuth, Flask-SimpleLDAP et python-dotenv
- Création d'un volume pour stocker le fichier "student_age.json"
- Exposition du port 5000 pour l'API
- Définition du point d'entrée pour lancer le script "student_age.py"

### 2. Déploiement avec Docker Compose
- Création du fichier docker-compose.yml
- Déploiement de deux services :
  - "website" basé sur l'image php:apache, avec variables d'environnement, montage du répertoire web et dépendance au service API
  - "API" utilisant l'image construite précédemment, avec montage du fichier "student_age.json"
- Vérification du bon fonctionnement de l'application web en affichant la liste des étudiants (capture d'écran)

### 3. Registre Docker privé
- Déploiement d'un registre Docker privé (ou utilisation de Portus)
- Envoi de l'image de l'API sur le registre privé
- Visualisation des images dans l'interface web du registre

## Résultats
- L'application POZOS est désormais conteneurisée et facile à déployer grâce à Docker Compose
- Les images Docker sont stockées dans un registre privé sécurisé
- L'ensemble de l'infrastructure est modulaire, évolutive et portable

## Compétences acquises
- Maîtrise de la construction d'images Docker personnalisées
- Utilisation avancée de Docker Compose pour le déploiement d'applications multi-services
- Mise en place d'un registre Docker privé pour la gestion des images
