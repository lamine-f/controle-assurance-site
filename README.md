# Contrôle Assurance, le site

La page de présentation de l'app Android Contrôle Assurance, avec le lien de téléchargement de l'APK. Une page
statique (`index.html`), publiée sur Vercel.

## L'APK

L'APK n'est pas dans le dépôt : il est joint à une release GitHub, sous le nom fixe `controle-assurance.apk`. Le
bouton de la page pointe vers `releases/latest/download/controle-assurance.apk`, donc toujours vers la dernière
release.

Pour publier une nouvelle version :

1. Compiler l'APK de release, signé par la clé de release (voir `plugins/with-release-signing.js` dans le dépôt de
   l'app). Chaque version doit porter la même signature, sinon elle ne s'installe pas par-dessus la précédente.
2. `gh release create v<version> controle-assurance.apk --title "<version>" --notes "…"`
3. Mettre à jour dans `index.html` la version, la taille et l'empreinte SHA-256 (`shasum -a 256 controle-assurance.apk`).
