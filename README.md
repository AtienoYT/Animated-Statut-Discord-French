# Animated-Statut-Discord-French

Le plugin Animated statut de BetterDiscord entièrement traduit en Français pour votre plus grand plaisir


# Installation

Installe BetterDiscord
Télécharge animated-status.plugin.js dans le répertoire suivant

Mac: ~/Library/Preferences/BetterDiscord

Windows: %appdata%\BetterDiscord\plugins

Linux: ~/.config/BetterDiscord/plugins


# Usage

Ouvrez Discord, allez dans Paramètres> Plugins, activez AnimatedStatus et cliquez sur Paramètres.
Entrez les informations requises dans les champs de saisie et cliquez sur Enregistrer


# Délai d'expiration / temps par image clé

La valeur spécifie la durée de chaque étape d'animation en millisecondes. Exemple: avec un délai d'expiration de 2000, l'animation suivante prendrait 4 secondes pour se terminer

"abc"
"def"

Pour empêcher le serveur Discord d'être spammé avec des demandes, le délai d'expiration minimum autorisé est codé en dur à 2,9 secondes.
Logiquement, le délai d'expiration de l'animation doit être d'au moins 29 000, au mieux de 10 000 millisecondes (10 secondes) pour que l'animation soit fluide sur les autres clients.
Dans l'application mobile, l'état n'est pas mis à jour de manière cohérente, c'est-à-dire que la liste des membres du serveur est mise à jour en fonction des actions des utilisateurs dans l'application. Ne soyez pas surpris si l'animation ne semble pas fluide ou saute des images.

^ D'après @pintoso


# éditeur 'riche' vs 'brut'

Depuis la dernière version, le plugin dispose désormais d'un nouvel éditeur riche. Cela n'ajoute pas de fonctionnalités, mais rend l'édition de vos animations beaucoup plus facile!

![image](https://user-images.githubusercontent.com/46424664/113426784-42eb5180-93d4-11eb-85de-d0f9cc67ccb6.png)

L'éditeur brut n'est qu'un champ de saisie de texte, dans lequel vous pouvez modifier vos animations manuellement dans un format de type json
(regarder le code source révèle qu'il s'agit essentiellement de json avec des crochets manquants)


# Animations

![image](https://user-images.githubusercontent.com/46424664/113427178-e2a8df80-93d4-11eb-878c-de088bf2de8c.png)

Les animations sont réalisées dans une syntaxe vraiment simple et facile à comprendre.


"Test (Message)"
"Test (Message)", "👍 (Symbol)"
"Test (Message)", "emoji (Nitro Symbol)", "000000000000000000 (Nitro Symbol ID)"
"eval new String('test') (Javascript)"
"eval new String('test') (Javascript)", "eval new String('👍') (Javascript)"
...


# Examples

Switching text:

"Text 1"
"Text 2 with emoji", "👍"


# Discord Nitro Emoji

Ouvrez un chat Discord, tapez \.

![image](https://user-images.githubusercontent.com/46424664/113427334-200d6d00-93d5-11eb-8747-e470cd3ba6df.png)

- Sélectionnez les emojis que vous souhaitez inclure dans votre statut à l'aide du sélecteur d'emojis.

![image](https://user-images.githubusercontent.com/46424664/113427366-2c91c580-93d5-11eb-82c2-d78e21765eed.png)

- Notez que le message est devenu «<: emojiname: emojiid>». Les valeurs entre crochets (emojiname et emojiid) sont les valeurs requises pour le statut.

![image](https://user-images.githubusercontent.com/46424664/113427389-36b3c400-93d5-11eb-97f7-558d3993508b.png)

- Modifiez les paramètres en conséquence

![image](https://user-images.githubusercontent.com/46424664/113427781-edb03f80-93d5-11eb-8014-914cbab9965c.png)


# Javascript personnalisé

Ayez l'heure actuelle comme statut:

"eval let fmt=t=>(t<10?'0':'')+t;let d=new Date();`${fmt(d.getHours())}:${fmt(d.getMinutes())}:${fmt(d.getSeconds())}`;"

Avoir l'heure actuelle avec le symbole d'horloge correspondant comme statut actuel ![image](https://user-images.githubusercontent.com/46424664/113427911-2e0fbd80-93d6-11eb-8831-3e5f61c014f5.png)

"eval let fmt=t=>(t<10?'0':'')+t;let d=new Date();`${fmt(d.getHours())}:${fmt(d.getMinutes())}:${fmt(d.getSeconds())}`;", "eval ['🕛','🕐','🕑','🕒','🕓','🕔','🕕','🕖','🕗','🕘','🕙','🕚'][((new Date()).getHours()%12)];"
