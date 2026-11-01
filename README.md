# Design System Library : application Android

Application Android (WebView) qui affiche la Design System Library, incluse dans `app/src/main/assets/index.html`.

## Icône

L'icône est définie dans `app/src/main/res/drawable/ic_launcher_foreground.xml` (motif) et `app/src/main/res/values/colors.xml` (couleur de fond `ic_launcher_background`). Pour la changer, remplacez ces deux fichiers. L'icône est adaptative : elle s'adapte aux formes d'écran (cercle, carré arrondi).

## Mettre le projet sur GitHub

1. Créez un dépôt vide sur github.com.
2. Dans le dossier du projet :

   git init
   git add .
   git commit -m "Première version"
   git branch -M main
   git remote add origin https://github.com/VOTRE-COMPTE/VOTRE-DEPOT.git
   git push -u origin main

3. Onglet **Actions** du dépôt : le workflow « Build APK » se lance automatiquement.
4. Une fois terminé, ouvrez le run et téléchargez l'artifact **DesignSystemLibrary-debug-apk** (fichier `app-debug.apk`).
5. Copiez l'APK sur le téléphone et installez-le (autorisez l'installation depuis une source inconnue).

## Compiler en local

Prérequis : Android Studio (ou Android SDK), JDK 17.

   gradle wrapper --gradle-version 8.7
   ./gradlew assembleDebug

L'APK est généré dans `app/build/outputs/apk/debug/app-debug.apk`.

## Publication (Google Play)

Une version de publication nécessite une signature : créez un keystore, puis ajoutez la configuration de signature et lancez `./gradlew bundleRelease`. Ce n'est pas configuré dans ce modèle.

## Remarques

- L'application utilise Internet pour charger les polices Google Fonts. Sans connexion, les polices système sont utilisées.
- Les fichiers téléchargés (CSS, ZIP, JSON, etc.) sont enregistrés dans le dossier Téléchargements.
- Pour mettre à jour l'application, remplacez `app/src/main/assets/index.html` et incrémentez `versionCode` dans `app/build.gradle`.

## Logo et icône

- Icône de l'application : fond bleu `#2E3192` (`values/colors.xml`) et emblème blanc (`mipmap-*/ic_launcher_foreground.png`), extrait du logo Design System Library.
- Icône pour la fiche Play Store : `store/playstore-icon-512.png` (512 × 512 px).
