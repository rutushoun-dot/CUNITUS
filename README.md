# Cunitus — prototype installable et projet Android

## Ce qui est prêt
- `index.html` : application web autonome de gestion cunicole.
- `manifest.webmanifest`, `service-worker.js`, `icons/` : base PWA installable après hébergement en HTTPS.
- `android_app/` : projet source Android Studio qui ouvre l'interface dans une WebView locale, sans connexion réseau nécessaire pour l'interface.

## Important : ce n'est pas encore un APK compilé
Je ne peux pas déclarer qu'un APK est prêt tant qu'il n'a pas été compilé avec Android SDK/Gradle et testé sur un appareil. L'environnement de génération actuel ne dispose pas de la chaîne Android complète. Le projet `android_app/` est fourni pour la compilation dans Android Studio.

## Construire l'APK dans Android Studio
1. Installe Android Studio sur un ordinateur.
2. Ouvre le dossier `android_app`.
3. Laisse Gradle télécharger les composants requis (connexion Internet nécessaire pour cette étape).
4. Dans le menu Build, choisis **Build APK(s)**.
5. Installe l'APK de test sur ton téléphone Android et vérifie les fonctions avant usage réel.

## Installer la version PWA
La PWA doit être publiée sur un hébergement HTTPS. Ouvre son adresse dans Chrome Android, puis menu ⋮ > **Installer l'application** ou **Ajouter à l'écran d'accueil**. Le service worker met en cache les fichiers de l'application pour un usage hors ligne après le premier chargement.

## Données et limites
- Les données de l'élevage sont stockées localement sur l'appareil (localStorage). Elles ne sont pas synchronisées automatiquement entre appareils.
- Fais régulièrement un export JSON et conserve la sauvegarde ailleurs.
- Les notifications de navigateur ne garantissent pas des rappels si l'application est fermée. Pour des rappels Android fiables, il faudra ajouter et tester une planification native.
- Le calculateur de dilution fait un calcul proportionnel uniquement. Respecte l'étiquette du produit et les conseils vétérinaires; le calcul ne valide ni l'indication ni la sécurité du produit.
- Le calendrier de reproduction applique les repères demandés : palpation J+14, boîte à nid J+27, mise bas prévue J+30.
