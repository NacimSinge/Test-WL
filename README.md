# Wavelength Live pour Twitch (aucun code requis)

Cette page web vous permet de recréer gratuitement le jeu **Wavelength** avec votre chat Twitch. Tout se passe dans votre navigateur : pas besoin de connaître le code, GitHub ou d’installer un programme. Vous allez simplement télécharger un fichier et l’ouvrir.

## Ce dont vous avez besoin

- Un ordinateur (Windows ou Mac) utilisé pour streamer.
- Une connexion internet pour accéder au chat Twitch.
- Un navigateur moderne déjà installé (Chrome, Edge, Firefox, etc.).
- (Facultatif) OBS ou un logiciel de streaming si vous voulez afficher le jeu à l’écran.
- Votre chaîne Twitch et, si vous le souhaitez, un compte bot secondaire.

## Étape 1 – Télécharger le fichier du jeu

1. Ouvrez la page GitHub du projet (l’adresse où vous lisez ce guide) et cliquez sur le bouton vert **Code** en haut à droite de la liste des fichiers.
2. Choisissez **Download ZIP** (Télécharger ZIP). Un fichier compressé va se télécharger sur votre ordinateur.
3. Ouvrez le fichier ZIP (double-cliquez dessus). Si une fenêtre vous propose *Extraire tout*, acceptez, puis faites glisser le fichier **`index.html`** vers un dossier facile à retrouver (par exemple le Bureau).

> 💡 Vous n’avez besoin que de ce fichier `index.html`. Une fois qu’il est sur votre ordinateur, vous pouvez fermer l’onglet GitHub : tout se lance localement dans votre navigateur.

## Étape 2 – Ouvrir le jeu

1. Localisez le fichier `index.html` sur votre ordinateur.
2. Double-cliquez dessus : il s’ouvrira automatiquement dans votre navigateur.
3. Vous voyez maintenant l’interface du jeu prête à être configurée.

### L’intégrer à OBS (facultatif)

1. Ouvrez OBS.
2. Dans la scène de votre choix, cliquez sur le bouton **+** de la liste *Sources*.
3. Choisissez **Source navigateur** (Browser Source).
4. Dans le champ *URL*, tapez `file:///` puis collez le chemin complet vers `index.html`. Le plus simple : cliquez sur **Parcourir** (Browse) et sélectionnez le fichier.
5. Validez : l’interface du jeu s’affiche dans OBS.

## Étape 3 – Connecter le chat Twitch

Dans la partie gauche de l’interface :

1. **Chaîne Twitch** : écrivez simplement le nom de votre chaîne (sans `#`). Exemple : `monstream`.
2. **Pseudo Twitch du bot** :
   - Laissez ce champ vide si vous ne faites que lire les messages du chat (c’est le cas le plus simple).
   - Remplissez-le avec un compte bot si vous voulez que le jeu envoie des messages automatiques.
3. **Jeton OAuth** :
   - Laissez vide si vous êtes en mode lecture seule (connexion anonyme autorisée par Twitch).
   - Remplissez-le uniquement si vous avez indiqué un compte bot et disposez de son jeton.
4. Cliquez sur **Connexion**. Le voyant passe au vert avec le texte `Connecté au chat`.

> ❗ Si le voyant reste rouge : vérifiez l’orthographe de votre chaîne ou relancez votre navigateur.

## Étape 4 – Jouer une manche

1. Indiquez les deux extrêmes (ex. `0 = Froid`, `100 = Chaud`).
2. Cliquez sur **Générer une valeur** : une valeur secrète apparaît dans le panneau bleu.
3. Masquez la valeur (bouton **Afficher / Masquer**) avant de retourner sur la scène en direct.
4. Expliquez au chat qu’il doit taper `!` suivi d’un nombre (exemple `!42`).
5. Les votes apparaissent automatiquement : suivez la moyenne, le nombre de votants et le dernier message reçu.
6. Quand vous le souhaitez, cliquez sur **Révéler la cible & l'écart** pour montrer la valeur exacte et la moyenne du chat.
7. Cliquez sur **Réinitialiser les votes** pour passer au tour suivant.

## (Optionnel) Obtenir un jeton OAuth pour un bot

Vous n’en avez pas besoin pour lire le chat. Si vous souhaitez qu’un compte bot envoie des messages, créez un compte Twitch secondaire et suivez l’une des méthodes suivantes :

1. **Méthode officielle Twitch** (plus technique) : guide complet ici <https://dev.twitch.tv/docs/irc/authenticate-bot/>.
2. **Générateur simple** : <https://twitchtokengenerator.com/quick/tmi> (sélectionnez les permissions `chat:read` et `chat:edit`).

Dans les deux cas, copiez la chaîne de caractères qui commence par `oauth:` et collez-la dans le champ *Jeton OAuth*.

> Gardez ce jeton secret : il donne accès au compte bot.

## Résolution de problèmes courants

- **Rien ne s’affiche dans OBS** : vérifiez que l’URL pointe bien vers le fichier `index.html` (avec `file:///`).
- **Le statut reste déconnecté** : assurez-vous que votre chaîne Twitch est correctement orthographiée et que vous avez cliqué sur **Connexion**.
- **Les votes ne bougent pas** : rappelez au chat de taper un `!` avant le nombre (`!50`, `!73`, etc.).
- **Vous avez changé de scène et perdu la connexion** : cliquez sur **Déconnexion** puis **Connexion** pour relancer.

## Personnaliser le visuel (facultatif)

Si vous vous sentez à l’aise, vous pouvez ouvrir `index.html` avec un éditeur de texte (Bloc-notes, VS Code) pour changer les couleurs ou les textes. Ne modifiez pas le reste du fichier si vous n’êtes pas sûr de ce que vous faites.

Bon stream et amusez-vous bien avec votre version Live de Wavelength !
