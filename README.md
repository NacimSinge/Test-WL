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
3. **Renseignez vos identifiants Twitch** :
   - *Chaîne Twitch* : le nom de votre chaîne sans le `#`.
   - *Pseudo Twitch du bot* : votre compte ou un compte bot secondaire.
   - *Jeton OAuth* :
     1. Visitez [https://twitchapps.com/tmi/](https://twitchapps.com/tmi/) (site officiel utilisé par la communauté).
     2. Connectez-vous avec le compte qui enverra les messages.
     3. Copiez la clé générée (elle commence par `oauth:`) et collez-la dans le champ « Jeton OAuth ».
4. Cliquez sur **Connexion**. Le statut doit passer au vert (`Connecté au chat`).

> 💡 Pour plus de sécurité, vous pouvez créer un compte Twitch secondaire dédié au bot.

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
