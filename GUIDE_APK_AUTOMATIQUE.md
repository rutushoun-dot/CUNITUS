# Générer automatiquement l'APK Cunitus depuis GitHub

Ce projet est configuré pour compiler automatiquement un APK Android de test dans GitHub Actions. Tu n'as pas besoin d'écrire du code, mais une courte mise en place sur GitHub est nécessaire.

## Étapes depuis un téléphone Android

1. Télécharge et décompresse `Cunitus_application_android_source.zip` sur ton téléphone si ton gestionnaire de fichiers le permet. Le dossier à envoyer à GitHub est le contenu du projet, notamment les dossiers `.github` et `android_app`, ainsi que `index.html`, `manifest.webmanifest`, `service-worker.js`, `icons` et `README.md`.
2. Connecte-toi à GitHub ou crée un compte sur https://github.com.
3. Crée un nouveau dépôt, par exemple `cunitus-app`. Pour ce premier essai, tu peux le mettre privé.
4. Envoie les fichiers du projet dans ce dépôt. Important : le dossier caché `.github/workflows/build-apk.yml` doit aussi être envoyé. Si l'interface mobile rend l'envoi difficile, fais cette étape sur un ordinateur ou demande à une personne de confiance de t'aider.
5. Ouvre l'onglet **Actions** du dépôt. Si GitHub demande d'autoriser les workflows, accepte.
6. Le workflow démarre normalement lors du premier push. Sinon, sélectionne **Construire l'APK Cunitus** puis **Run workflow**.
7. Quand l'exécution est terminée avec une coche verte, ouvre l'exécution et cherche **Artifacts** puis **Cunitus-debug-APK**.
8. Télécharge et décompresse cet artefact : il contient `app-debug.apk`. Ouvre-le sur ton téléphone pour l'installer. Android peut demander d'autoriser l'installation depuis cette source.

## Important
- C'est un APK **debug de test**, non signé pour une publication sur Google Play.
- Le succès de la compilation ne remplace pas un test sur téléphone. Vérifie l'ajout/modification des animaux, les cages, les dates de reproduction, les soins, les sauvegardes et la restauration.
- Les données restent locales à l'appareil. Export JSON régulièrement et garde une copie ailleurs.
- Les rappels lorsque l'application est complètement fermée ne sont pas garantis par cette version : une planification native Android reste à développer pour des notifications fiables.
- Les dates J+14, J+27 et J+30 suivent les repères demandés pour ce projet. Le calculateur de dilution est proportionnel et ne vérifie pas la sécurité ni l'indication d'un produit.
