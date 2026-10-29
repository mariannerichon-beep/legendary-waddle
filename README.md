# La Famille en Jeu — PWA

## Contenu
- `index.html` : le jeu complet, responsive et interactif.
- `manifest.webmanifest` : identité et paramètres d'installation.
- `sw.js` : cache hors ligne de base.
- `icon.svg`, `icon-192.png`, `icon-512.png` : icônes de l'application.

## Mise en ligne (méthode simple : GitHub Pages)
1. Décompressez le ZIP.
2. Créez un dépôt GitHub vide.
3. Téléversez tous les fichiers du dossier à la racine du dépôt (pas le dossier ZIP lui-même).
4. Dans **Settings → Pages**, choisissez la publication depuis la branche principale et le dossier `/ (root)`.
5. Attendez la publication et ouvrez l'adresse fournie par GitHub Pages. L'adresse doit être en HTTPS.
6. Ouvrez le site une première fois en ligne pour permettre au cache de préparer les fichiers.

Les noms `index.html`, `manifest.webmanifest` et `sw.js` doivent rester inchangés et dans le même dossier. Le service worker nécessite HTTPS (ou localhost pour les tests). Ouvrir directement `index.html` en `file://` permet de jouer, mais pas d'installer la PWA ni d'utiliser le cache hors ligne.

## Installer sur téléphone
- **Android / Chrome ou navigateur compatible** : ouvrez le site HTTPS, puis utilisez le menu du navigateur → **Installer l'application** ou **Ajouter à l'écran d'accueil**. Le bouton d'installation peut aussi apparaître si le navigateur le propose.
- **iPhone / iPad (Safari)** : ouvrez le site HTTPS → **Partager** → **Sur l'écran d'accueil** → **Ajouter**. Selon la version iOS, l'intitulé peut varier.
- **Ordinateur (Chrome / Edge)** : ouvrez le site HTTPS ; utilisez l'icône d'installation dans la barre d'adresse ou le menu du navigateur → **Installer La Famille en Jeu**.
- **macOS Safari** : si l'option est proposée par la version du système, utilisez le menu de partage ou le menu Fichier pour ajouter le site au Dock.

## Hors ligne et données
Après une première visite en ligne réussie, les fichiers de base peuvent rester disponibles hors ligne grâce au service worker. Le jeu n'envoie pas les prénoms à un serveur et n'utilise pas de compte. La progression actuelle est en mémoire de la page : elle est réinitialisée si vous rechargez ou fermez complètement la page. Les données ne sont pas synchronisées entre appareils.

## Dépannage
- Si l'installation n'apparaît pas : vérifiez HTTPS, que le manifeste et les deux icônes se chargent, puis rechargez le site.
- Après modification du jeu, changez `famille-en-jeu-v1` dans `sw.js` en `famille-en-jeu-v2` pour renouveler le cache.
- Si une ancienne version persiste, fermez l'application installée puis rechargez le site dans le navigateur.
