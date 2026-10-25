# Psoa : version de test (GitHub + Render)

Ce dossier met Psoa en ligne gratuitement pour que des personnes la testent avec un simple lien. Il n'y a ni compte, ni paiement, ni serveur : tout est enregistré sur l'appareil de chaque testeur.

Tous les fichiers sont à la racine, sans sous-dossier : on peut donc les envoyer sur GitHub depuis un ordinateur comme depuis un téléphone.

## Étape 1. Mettre les fichiers sur GitHub

1. Créez un compte sur github.com si vous n'en avez pas.
2. Créez un dépôt : **+** (en haut), puis **New repository**. Nom : `psoa`. Choisissez **Public**, puis **Create repository**.
3. Sur la page du dépôt vide, touchez **uploading an existing file**.
4. Ajoutez **tous** les fichiers de ce dossier (index.html, config.js, manifest.webmanifest, sw.js, les 4 icônes png, avertissement-medical.html, README.md). Sur ordinateur, glissez-les ; sur téléphone, touchez « choose your files » et sélectionnez-les.
5. Touchez **Commit changes**. Vérifiez que `index.html` apparaît bien dans la liste des fichiers du dépôt.

## Étape 2. Publier avec Render

1. Allez sur render.com et connectez-vous avec votre compte GitHub.
2. **New +**, puis **Static Site**. Autorisez Render à lire votre dépôt `psoa` et sélectionnez-le.
3. Réglages :
   - **Branch** : `main`
   - **Build Command** : laissez vide
   - **Publish Directory** : laissez vide, ou mettez un point `.`
4. Touchez **Create Static Site** et attendez la fin du déploiement.
5. Render vous donne un lien de la forme `https://psoa.onrender.com` (le nom peut varier). **C'est ce lien que vous partagez.**

Les sites statiques sont proposés gratuitement par Render ; vérifiez les conditions et limites actuelles sur sa page de tarifs.

## Étape 3. Recevoir les avis

Psoa ne collecte aucune donnée : vous ne verrez donc pas qui l'utilise ni ce qui bloque. Le plus simple est un formulaire :

1. Créez un formulaire gratuit (Google Forms, Tally...) avec quelques questions : l'inscription était-elle claire ? les animations étaient-elles compréhensibles ? un exercice vous a paru faux ? le son vous a-t-il gêné ? que manque-t-il ?
2. Copiez le lien du formulaire.
3. Sur GitHub, ouvrez `config.js`, touchez le crayon, collez le lien entre les guillemets de `FEEDBACK_URL`, puis **Commit changes**.
4. Un bouton **Donner mon avis** apparaît dans l'onglet Profil de l'application.

Si votre formulaire demande une adresse e-mail ou d'autres données personnelles, prévenez clairement les testeurs de l'usage que vous en ferez.

## Étape 4. Mettre à jour pendant les tests

Quand je vous donne un nouveau fichier `index.html` :

1. Sur GitHub, touchez **Add file**, puis **Upload files**.
2. Déposez le nouveau `index.html` (même nom) et touchez **Commit changes**.
3. Render republie tout seul en une à deux minutes. Les testeurs voient la nouvelle version en rechargeant la page.

## Ce qu'il faut dire aux testeurs

- Ouvrez le lien **sur votre téléphone**.
- Faites le parcours d'inscription, puis **une séance complète**, jusqu'à la note de difficulté.
- Essayez le son (sur iPhone, vérifiez que le mode silencieux n'est pas activé).
- Optionnel : ajoutez Psoa à l'écran d'accueil (iPhone : Safari, Partager, Sur l'écran d'accueil ; Android : menu, Installer l'application).
- Vos données restent sur votre téléphone. Pour tout effacer : Profil, Effacer mes données.
- Notez tout ce qui vous paraît bizarre (mouvement faux, texte incompréhensible, bouton introuvable) et envoyez-le via le bouton « Donner mon avis ».

## En cas de problème

- **Page blanche ou 404** : vérifiez que `index.html` est bien à la racine du dépôt (et non dans un dossier) et que « Publish Directory » est vide.
- **Ancienne version affichée** : rechargez la page ; en dernier recours, fermez et rouvrez l'onglet.
- **Pas de son** : touchez d'abord un bouton de l'appli (les navigateurs l'exigent), vérifiez le volume et le mode silencieux.
- **Les formules payantes** : elles sont masquées dans cette version. Pour les montrer (simulées), mettez `SHOW_PAYWALL: true` dans `config.js`.

## Plus tard

Le dossier `psoa-production` (livré séparément) contient la version avec comptes, vrais paiements Stripe, rappels et pages légales, à utiliser quand les tests seront concluants.
