# Détection en temps réel d'une main avec TensorFlow

Ce projet a été réalisé durant ma première année à CentraleSupélec (2022), dans le cadre de ma participation à l'association **Automatant**, centrée sur les applications de l'intelligence artificielle.

L'objectif était de **reproduire et comprendre un système de détection en temps réel d'une main**, à partir d’un **papier de recherche** publié par une équipe spécialisée en IA. Le travail reposait sur l’étude, la réécriture et l’expérimentation à partir d’un **code source partiellement fourni** par cette équipe.

---

## 🔍 Objectif

- Reproduire les résultats du papier de recherche sur la détection de la main.
- Comprendre le fonctionnement d’un pipeline de détection temps réel.
- Utiliser un **dataset d’images de mains** pour entraîner un modèle basé sur **TensorFlow**.
- Adapter le modèle à une exécution en temps réel via une webcam.

---

## 🧠 Technologies

- **Python**
- **TensorFlow 2.x**
- **OpenCV** (pour la capture vidéo en temps réel)
- Jupyter / Google Colab (environnement de travail)
- Dataset d'images de mains (référence dans le notebook)

---

## 🧪 Fondements théoriques

Ce projet repose sur plusieurs concepts fondamentaux de l’intelligence artificielle théorique :

### Apprentissage supervisé

Le modèle est entraîné à partir de couples (image, coordonnées des articulations), typiques de l’apprentissage supervisé. Il apprend une fonction de régression qui prédit la position des points clés d'une main à partir d’une image en entrée.

### Réseaux de neurones convolutifs (CNN)

Le cœur du modèle est un CNN, architecture bien adaptée aux tâches de vision par ordinateur. Les CNN sont capables de détecter automatiquement des motifs visuels hiérarchiques, tout en étant invariants aux translations locales.

### Régression de points clés

Contrairement aux tâches de classification, le modèle ne prédit pas des étiquettes, mais des coordonnées continues (régression). Chaque image est associée à 21 points d’intérêt, chacun représenté par un couple (x, y), soit 42 valeurs au total.

### Fonction de perte

Le modèle est optimisé par descente de gradient, avec une fonction de coût de type **MSE** (Mean Squared Error), qui pénalise l’écart entre les positions prédites et les vraies coordonnées des articulations.

### Généralisation et biais-variance

Le projet met en œuvre des stratégies classiques pour favoriser la généralisation du modèle (batching, normalisation, architecture adaptée), en évitant à la fois le surapprentissage et l’approximation trop grossière (compromis biais-variance).

### Prédiction structurée

Les coordonnées des articulations sont **structurellement liées** (ex : le pouce reste attaché à la paume). Bien que le modèle de base prédise chaque point indépendamment, la tâche elle-même est un exemple de prédiction structurée, avec des dépendances spatiales implicites.

---

## 📁 Contenu

- Notebook principal utilisé comme **fichier de prise de notes**, d’expérimentations, et de sauvegardes de mes apprentissages sur TensorFlow.
- Entraînement partiel du modèle sur un dataset.
- Début d’implémentation d’un pipeline de détection temps réel.

> ⚠️ Le projet est **incomplet**, car réalisé en collaboration avec un autre étudiant et interrompu avant finalisation complète.

---

## 📌 À noter

Ce projet m’a permis de me familiariser avec :
- les bases de **TensorFlow** (modèles, entraînement, sauvegarde, etc.)
- les concepts de **détection d’objets** et de **traitement d’image en temps réel**
- la lecture et l’exploitation de **travaux de recherche en IA**

Il constitue une **base de travail** et un **mémo personnel** sur mes premiers pas dans l’IA appliquée à la vision par ordinateur.

---

*Projet réalisé à titre exploratoire, dans le cadre d'une initiative associative.*
