# Wavelength Live pour Twitch

Cette mini-application 100% gratuite vous permet de jouer à une version "chat" du jeu Wavelength directement sur votre stream Twitch. Elle fonctionne dans n'importe quel navigateur moderne sans installation logicielle : il suffit d'ouvrir `index.html` en local (dans OBS vous pouvez ajouter la page comme "Browser Source").

## Fonctionnalités principales

- Connexion directe au chat Twitch via [`tmi.js`](https://tmijs.com/).
- Génération aléatoire d'une valeur secrète (0 à 100) cachée par défaut pour ne pas spoiler les viewers.
- Champ personnalisable pour les deux extrêmes de la manche.
- Lecture en temps réel des commandes `!nombre` envoyées par le chat.
- Calcul automatique de la moyenne des votes uniques du chat et suivi du dernier vote reçu.
- Bouton de révélation qui affiche la moyenne finale, la cible et l'écart.

## Mise en route (moins de 10 minutes)

1. **Téléchargez le dépôt** ou copiez simplement le fichier `index.html` sur votre ordinateur de streaming.
2. **Ouvrez le fichier** dans votre navigateur (clic droit → ouvrir avec Chrome/Edge/Firefox). Pour l'afficher sur OBS, ajoutez-le comme *Browser Source* en pointant vers `file:///…/index.html`.
3. **Configurez la connexion au chat** :
   - *Chaîne Twitch* : le nom de votre chaîne sans le `#` (obligatoire).
   - *Pseudo Twitch du bot* : laissez vide si vous ne faites que lire le chat. Remplissez-le si vous disposez d’un compte bot dédié.
   - *Jeton OAuth* : laissez vide pour une connexion anonyme (lecture seule). Si vous renseignez un pseudo bot, ajoutez également son jeton OAuth.
4. Cliquez sur **Connexion**. Le statut passera en vert (`Connecté au chat`) une fois la connexion établie.

> 💡 Pour plus de sécurité, créez un compte Twitch secondaire dédié au bot si vous souhaitez envoyer des messages automatisés.

### Générer un jeton OAuth (optionnel)

L’application peut lire le chat Twitch en mode anonyme, ce qui suffit pour la majorité des usages. Vous n’avez donc pas besoin de token tant que vous n’envoyez pas de messages via le bot.

Si vous voulez tout de même authentifier un compte bot, deux possibilités :

1. **Méthode officielle Twitch** (recommandée par la documentation) :
   - Créez une application sur <https://dev.twitch.tv/console/apps> et notez le `Client ID` et le `Client Secret`.
   - Ajoutez `http://localhost` dans la liste des *Redirect URIs*.
   - Suivez le guide <https://dev.twitch.tv/docs/irc/authenticate-bot/> pour obtenir un token `chat:read chat:edit` et copiez la valeur qui commence par `oauth:`.
2. **Générateur communautaire maintenu** : <https://twitchtokengenerator.com/quick/tmi> propose une interface simplifiée pour générer un token `chat:read`/`chat:edit`. Connectez-vous avec le compte bot, copiez le token (préfixe `oauth:`) et collez-le dans le champ prévu.

> ℹ️ Quel que soit le procédé utilisé, traitez votre token comme un mot de passe : ne le partagez pas et régénérez-le en cas de doute.

## Jouer une manche

1. Saisissez les deux extrêmes (0 = gauche, 100 = droite).
2. Cliquez sur **Générer une valeur** : la cible aléatoire apparaît dans le cartouche secret.
3. Masquez la valeur (`Afficher / Masquer`) avant de remettre la scène sur votre stream.
4. Lancez le chrono oralement et demandez au chat d'envoyer `!0` à `!100`.
5. Observez la moyenne en direct, le nombre de votants et le dernier vote.
6. Quand le temps est écoulé, cliquez sur **Révéler la cible & l'écart** pour afficher le résultat final.
7. Cliquez sur **Réinitialiser les votes** pour préparer le tour suivant.

## Bonnes pratiques

- Seul le dernier vote d'un viewer est conservé pour éviter le spam : le bot met automatiquement la moyenne à jour.
- L'interface ne stocke rien sur un serveur : toutes les données restent dans votre navigateur.
- Si la connexion au chat tombe, appuyez sur **Déconnexion** puis **Connexion**.

## Personnalisation

Le fichier est autonome : vous pouvez ajuster les couleurs ou les textes directement dans `index.html`. Pour toute modification, gardez la structure HTML/JS existante afin de ne pas casser la connexion au chat.

Bon stream et amusez-vous bien avec votre version Live de Wavelength !
