# Premiers pas avec Docker sur Jetson NANO (M2 IA 2024)

## Objectifs

Créer un Dockerfile permettant de construire une image compatible Jetson NANO.

Cette image doit :
- Virtualiser un environnement Jetson NANO
- Installer les dépendances de YOLOv5 ou YOLOv8
- Donner l'accès aux caméras CSI et les librairies CUDA de la carte
- Cloner le repository git contenant votre programme
- Lancer automatiquement votre programme et se connecter au $DISPLAY de la jetson nano pour le visualiser

## Ressources

- 🔵 Discord pour voir les indices et poser des questions : https://discord.gg/wg8fT47Gmr
- 📝 Diapo avec quelques notions de cours : https://www.canva.com/design/DAF8TAmXd4g/1U2dHzQSmeVHDqQKXNQf3w/view?utm_content=DAF8TAmXd4g&utm_campaign=designshare&utm_medium=link&utm_source=editor
- 🐋 Docker : https://www.docker.com/
- 📦 Docker images : https://catalog.ngc.nvidia.com/orgs/nvidia/containers/l4t-ml
- 🧠 Ultralytics : https://docs.ultralytics.com/fr

## Cheminement

### 🥚 Pré-requis
- Installer Docker (ou vérifier s'il est déjà installé ?)
- Comprendre les notions suivantes :
  - Image Docker
  - Conteneur Docker
  - Dockerfile
  - Différence entre un conteneur et une VM

### 🐣 Premiers pas avec Docker
- Choisir une image Docker "socle" sur laquelle votre projet sera basé
- Créer un container de l'image socle de base
  - `docker run [...]` (indices sur discord si vous ne trouvez pas, mais expérimentez vous-même avant)
- Se connecter au container, manipuler l'environnement

### 🐥 Premiers pas avec Dockerfile
- Créer un Dockerfile (c'est un fichier sans extension, juste "Dockerfile")
- Importer l'image "socle"
- Ajouter quelques commandes de base, par exemple `mkdir YOLO`
- Build l'image, créer un container et s'y connecter pour constater si les commandes du Dockerfile ont fonctionné

### 🐓 Vérifier le fonctionnement de YOLO dans le container
Dans le Dockerfile:
- Cloner YOLOv5
- Installer Python s'il n'est pas présent de base dans l'image (>3.7 conseillé, utilisation de pyEnv conseillée)
- Installer les dépendances de YOLO
- Build l'image, créer un container et s'y connecter pour voir si les fonctions de base de YOLO fonctionnent
  - `docker build [...]` (indices sur discord si vous ne trouvez pas, mais expérimentez vous-même avant)

### 🦉 Automatiser l'application avec Docker
Dans le Dockerfile:
- Cloner votre repository, et YOLO
- Installer tous les pré-requis de votre application et de YOLO
- Lancer automatiquement votre programme au démarrage du container
