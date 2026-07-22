# Jour 3 - Chronomètre, pouvoir, niveau final et boss

## Objectif de la journée

Le jour 3 sert à terminer la boucle principale du jeu en ajoutant des mécaniques plus avancées et une vraie conclusion.

À la fin de la journée, le projet contient :

- un chronomètre global affiché dans le HUD et dans la scène de victoire ;
- une potion de mana qui augmente la variable globale `power` ;
- une épée lancée que le joueur peut utiliser en consommant du `power` ;
- une barre de ressource pour afficher le `power` ;
- un troisième niveau créé à partir du niveau 2 ;
- une zone de boss dans le niveau final ;
- un boss requin géant avec de la vie, des animations et une activation par zone de détection ;
- un diamant qui apparaît après la mort du boss et permet d'aller vers la victoire ;
- des indications de tutoriel dans les premiers niveaux.

La journée est organisée autour de cinq fiches :

| Fiche | Sujet |
|:--|:--|
| `1_reprise.md` | Vérification du jeu et ajout du chronomètre |
| `2_capacite_spécial.md` | Potion de mana, épée lancée et barre de pouvoir |
| `3_niveau_final.md` | Création du niveau 3 et de la zone du boss |
| `4_boss.md` | Création du boss requin et de ses événements |
| `5_tutorial.md` | Ajout d'indications dans les niveaux 1 et 2 |

## 1. Reprise et vérification

Avant d'ajouter de nouvelles mécaniques, le projet est testé pour vérifier que les éléments des jours précédents fonctionnent toujours.

On vérifie notamment :

- le passage entre les niveaux ;
- les ennemis ;
- les objets à récupérer ;
- la vie du joueur ;
- le score ;
- les scènes de victoire et de défaite ;
- les variables globales déjà utilisées.

Cette étape permet de repartir sur une base stable avant d'ajouter le contenu final.

## 2. Chronomètre global

Un chronomètre global est ajouté pour mesurer le temps de jeu.

La variable globale utilisée est :

| Nom        |  Type  | Valeur de départ |
|:-----------|:------:|:----------------:|
| globalTime | nombre |        0         |

Le chronomètre fonctionne ainsi :

- dans le niveau 1, `globalTime` est remis à 0 au début de la partie ;
- dans les niveaux suivants, `globalTime` continue d'augmenter ;
- à chaque mise à jour du jeu, on ajoute le temps écoulé à `globalTime` ;
- un objet `Texte` global affiche la valeur du chronomètre dans le HUD ;
- la scène de victoire affiche le temps final avec le texte `"Votre chrono : " + globalTime`.

Le chronomètre permet de donner un objectif supplémentaire au joueur : finir le jeu le plus vite possible.

## 3. Potion de mana et variable `power`

Un nouveau collectible est créé avec la potion bleue. Cette potion sert à augmenter la variable globale `power`.

La logique mise en place est la suivante :

- le joueur touche une potion de mana ;
- la variable globale `power` augmente de 1 ;
- la valeur de `power` est limitée à 4 avec `min()` ;
- la potion est supprimée après avoir été ramassée ;
- l'événement est copié dans les autres niveaux.

Cette mécanique prépare l'utilisation de la capacité spéciale.

## 4. Épée lancée

Une nouvelle version de l'épée est créée sous forme d'objet `Sprite`. Elle utilise l'image du dossier `sword/23-sword embedded`.

L'objet est ensuite configuré :

- le point d'origine est placé au niveau du manche ;
- l'objet est mis dans les objets globaux ;
- le joueur peut le créer depuis le point `sword` ;
- le lancer consomme 2 points de `power`.

L'orientation du joueur est vérifiée avec deux événements :

- si le joueur regarde à gauche, l'épée est retournée et part vers la gauche ;
- sinon, l'épée part vers la droite.

Une force permanente est appliquée sur l'axe X pour déplacer l'épée en ligne droite.

## 5. Collision de l'épée lancée

L'épée lancée peut toucher les ennemis.

Quand elle entre en collision avec un ennemi :

- l'ennemi est supprimé ;
- l'épée lancée est supprimée ;
- le score augmente.

L'objet de l'épée lancée reçoit aussi le comportement `Détruire en dehors de l'écran`, afin qu'il disparaisse automatiquement lorsqu'il sort de la caméra.

## 6. Affichage du `power`

Pour que le joueur comprenne l'état de sa capacité spéciale, une barre de ressource est ajoutée dans le HUD.

La barre est configurée avec :

- une valeur initiale de 0 ;
- une valeur maximale de 4 ;
- le calque `HUD` ;
- un statut d'objet global pour être réutilisée dans tous les niveaux.

Dans les événements, la valeur de la barre est mise à jour avec la valeur de la variable globale `power`.

## 7. Création du niveau final

Le niveau final est créé en dupliquant le niveau 2. Cette méthode permet de conserver les événements déjà construits.

Une fois la scène `Niveau 3` créée :

- on vérifie que l'on travaille bien dans la bonne scène ;
- on cache temporairement le calque `HUD` ;
- on supprime les éléments du niveau 2 ;
- on réaffiche le calque `HUD` ;
- on construit une nouvelle carte mêlant bateau et îles.

Les scènes sont ensuite reliées :

- dans le niveau 2, toucher le diamant envoie vers le niveau 3 ;
- dans le niveau 3, toucher le diamant envoie vers la scène de victoire.

## 8. Zone de boss

Une zone spéciale est préparée dans le niveau 3 pour accueillir le boss.

Cette zone doit être assez plate pour que le boss puisse se déplacer correctement avec son comportement de plateforme.

Un objet `boss_detection` est créé :

- c'est un collider ;
- il est placé à l'entrée de la zone du boss ;
- il permet de détecter quand le joueur entre dans l'arène.

Cette détection servira à activer le boss uniquement lorsque le joueur arrive dans sa zone.

## 9. Création du boss

Le boss est un requin géant.

Un objet `Sprite` nommé `Boss` est créé avec les animations du dossier `requin`.

L'objet est configuré avec :

- un facteur de taille de 2 ;
- un comportement de vie ;
- un comportement d'objet de plateforme ;
- une variable d'objet `Active`, de type booléen, réglée sur `false` par défaut.

La variable `Active` permet de décider si le boss doit commencer à agir ou non.

## 10. Événements du boss

Un groupe d'événements `Boss` est créé pour organiser la logique du combat.

Les événements mis en place permettent de :

- activer le boss quand le joueur entre dans `boss_detection` ;
- faire avancer le boss vers le joueur uniquement sur l'axe X ;
- retourner le boss pour qu'il regarde toujours dans la bonne direction ;
- détecter les collisions entre les épées et le boss ;
- retirer de la vie au boss ;
- supprimer l'épée lancée après une collision ;
- jouer l'animation de dégâts ;
- jouer l'animation de mort ;
- revenir à l'animation `idle` après l'animation `hit` ;
- gérer l'animation `death` ;
- faire perdre 1 point de vie au joueur quand le boss l'attaque.

Le boss devient donc un ennemi plus complet que les ennemis précédents : il possède de la vie, des animations, une activation et une logique de déplacement.

## 11. Fin du niveau

Quand le boss meurt, un diamant apparaît sur lui.

La logique est la suivante :

- on vérifie que l'animation de mort du boss est terminée ;
- on crée un diamant à la position du boss ;
- le joueur peut récupérer ce diamant ;
- le diamant permet d'aller vers la scène de victoire.

Cette étape donne une vraie conclusion au niveau final.

## 12. Tutoriel dans les niveaux

Des indications sont ajoutées dans les niveaux 1 et 2 afin d'aider le joueur.

Dans le niveau 1, des objets `Texte` indiquent :

- les touches de déplacement ;
- la touche de saut ;
- l'action à utiliser face au premier ennemi.

Dans le niveau 2, des indications expliquent la touche liée au pouvoir. Deux potions de mana sont placées avant l'indication pour montrer qu'une action spéciale devient possible.

Ces indications rendent le jeu plus clair sans devoir expliquer les contrôles en dehors du niveau.

## Résultat attendu à la fin du jour 3

À la fin du jour 3, le jeu doit être jouable du début à la fin.

Le joueur peut :

- traverser les niveaux 1, 2 et 3 ;
- voir son temps de jeu ;
- récupérer des potions de mana ;
- charger la variable `power` ;
- lancer une épée à distance ;
- éliminer des ennemis avec cette épée ;
- voir sa jauge de pouvoir dans le HUD ;
- entrer dans une zone de boss ;
- combattre un boss requin géant ;
- récupérer le diamant final ;
- atteindre la scène de victoire avec son chronomètre.

Le projet possède ainsi une progression complète : apprentissage, exploration, nouvelle capacité, niveau final, combat de boss et victoire.
