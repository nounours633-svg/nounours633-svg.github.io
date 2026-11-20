# Préparation Android — Mon Carnet Routier

Ce dépôt héberge le domaine principal `https://nounours633-svg.github.io/` et le fichier `/.well-known/assetlinks.json`.
Le fichier `twa-manifest.json` décrit l'application Android Trusted Web Activity (TWA) et pointe vers la version actuelle du carnet publiée dans le dépôt projet `Mon-carnet-routier` : `https://nounours633-svg.github.io/Mon-carnet-routier/`.

## Éléments déjà en place
- Application web existante, conservée sans modification.
- Manifeste web : `https://nounours633-svg.github.io/Mon-carnet-routier/manifest.json`
- Association Android : `/.well-known/assetlinks.json`
- Identifiant Android prévu : `io.github.nounours633_svg.twa`

## Avant de fabriquer le fichier AAB
Il faut disposer d'une clé privée d'envoi (upload keystore) et de ses mots de passe. Le fichier `assetlinks.json` contient des empreintes publiques ; il ne contient pas la clé privée et ne permet pas de signer l'AAB.

Ne jamais déposer de fichier .keystore/.jks ni de mot de passe dans le dépôt GitHub. La clé doit être conservée en lieu sûr et, si la compilation est automatisée, fournie à GitHub Actions comme secret.

Les empreintes actuellement présentes dans `assetlinks.json` ont été reprises dans `twa-manifest.json` sans en choisir une seule. Il faudra confirmer dans Play Console laquelle correspond au certificat de signature de l'application et laquelle au certificat d'envoi, avant la première publication.

## Protection
Ne pas remplacer `index.html`, `manifest.json` ou `sw.js` pour générer l'application Android. Le paquet Android doit ouvrir le site existant.
