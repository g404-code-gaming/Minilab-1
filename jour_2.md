# Jour 2 - Ajouter un deuxième niveau pirate

## Objectif de la journée

Le jour 1 a déjà permis de créer une première version complète du jeu : le joueur peut se déplacer, récupérer des objets, combattre un ennemi, perdre et atteindre une fin de niveau.

Le jour 2 ne sert pas à refaire ou à simplement agrandir la première scène. Nous allons ajouter une vraie suite au jeu avec un deuxième niveau dans le thème pirate.

À la fin de la journée, le jeu devra contenir :

- le niveau du jour 1, toujours jouable ;
- un nouveau niveau 2 avec une ambiance de bateau ou de port pirate ;
- un nouvel ennemi, le crabe ;
- une clé ou un objet important à récupérer ;
- une sortie de niveau qui ne s'ouvre qu'après avoir récupéré cet objet ;
- une scène de victoire qui termine proprement le jeu si l'enfant ne revient pas au jour 3.

La journée est prévue pour durer environ 7 heures.

## Ce que nous gardons du jour 1

Avant de commencer, nous gardons tout ce qui fonctionne déjà :

- le joueur ;
- la caméra ;
- les pièces ;
- les potions ;
- le diamant ;
- le score ;
- la barre de vie ;
- l'épée ;
- l'ennemi étoile de mer ;
- la détection de chute dans le vide.

Ces éléments deviennent la base du jeu. Le jour 2 ajoute du contenu par-dessus cette base.

## 1. Test rapide du jeu existant

Durée estimée : 20 minutes

Nous lançons le projet pour vérifier que le jeu du jour 1 fonctionne encore.

À tester rapidement :

- le joueur se déplace correctement ;
- les pièces et le score fonctionnent ;
- l'épée peut battre l'ennemi ;
- la potion soigne le joueur ;
- le diamant termine le niveau.

Si une erreur bloque complètement le jeu, il faut la corriger. Sinon, nous avançons vers les nouveautés du jour 2.

## 2. Créer la scène du niveau 2

Durée estimée : 45 minutes

Nous allons créer une nouvelle scène pour le deuxième niveau.

Nom conseillé :

- "Niveau_2"

Le niveau 2 doit avoir une ambiance différente du niveau 1. Comme le projet a un thème pirate, nous pouvons utiliser le tileset de bateau.

Assets utiles :

- `assets/tileset/ship_tileset.png`
- `assets/background/BG Image.png`

Idée de décor :

- un pont de bateau ;
- des plateformes en bois ;
- des trous entre les planches ;
- des zones plus hautes comme des mâts ou des caisses ;
- une sortie à la fin du niveau.

Il faut garder le niveau assez court pour pouvoir le finir dans la journée. L'objectif est d'avoir un deuxième niveau jouable, pas une carte énorme.

## 3. Relier le niveau 1 au niveau 2

Durée estimée : 35 minutes

Au jour 1, le diamant servait de fin de niveau. Maintenant, il va servir à passer au niveau 2.

À faire :

- garder le diamant à la fin du niveau 1 ;
- modifier son action ;
- au lieu de recharger la scène, changer de scène vers "Niveau_2" ;
- vérifier que les variables globales sont conservées.

Variables à garder entre les scènes :

- `life`
- `coins`
- `score`
- `power`

Le joueur doit avoir l'impression de continuer la même aventure.

## 4. Ajouter un objectif dans le niveau 2

Durée estimée : 50 minutes

Le niveau 2 doit avoir un objectif différent du niveau 1.

Nous allons créer un objet important à récupérer avant de pouvoir finir le niveau.

Idées possibles :

- une clé de pirate ;
- un coffre ;
- une carte au trésor ;
- un cristal spécial ;
- un gros diamant utilisé comme trésor.

Pour rester simple, nous pouvons utiliser le diamant vert comme "trésor du bateau".

Nouvelle variable globale conseillée :

| Nom | Type | Valeur de départ |
|:--|:--:|:--:|
| hasTreasure | booléen | false |

Logique à créer :

- au début du niveau 2, `hasTreasure` vaut `false` ;
- quand le joueur touche le trésor, `hasTreasure` devient `true` ;
- le trésor disparaît ;
- le score augmente ;
- la sortie du niveau devient utilisable.

Cette mécanique donne un objectif clair au joueur : trouver le trésor avant de sortir.

## 5. Créer la sortie du niveau 2

Durée estimée : 40 minutes

Nous allons créer une sortie à la fin du niveau 2.

Idées de sortie :

- une porte de cabine ;
- une échelle ;
- un drapeau pirate ;
- une zone invisible appelée "SortieNiveau2".

La sortie doit fonctionner seulement si le joueur a récupéré le trésor.

Logique :

- si le joueur touche la sortie et que `hasTreasure` est `true`, il passe à la scène "Victoire" ;
- si le joueur touche la sortie et que `hasTreasure` est `false`, rien ne se passe ou un message indique qu'il faut trouver le trésor.

Message possible :

- "Trouve le trésor avant de partir !"

Cela permet de créer une vraie mission sans rendre le jeu trop compliqué.

## 6. Ajouter le crabe comme nouvel ennemi

Durée estimée : 1 heure

Nous allons ajouter un nouvel ennemi : le crabe.

Assets utiles :

- `assets/crabe/01-Idle`
- `assets/crabe/02-Run`

Le crabe doit être différent de l'étoile de mer.

Idées de comportement :

- il marche de gauche à droite ;
- il est placé sur les plateformes du niveau 2 ;
- il fait perdre 1 point de vie au joueur ;
- il peut être battu avec l'épée ;
- il rapporte plus de score que l'étoile de mer.

Valeur conseillée :

- étoile de mer battue : +150 points ;
- crabe battu : +250 points.

Il faut ajouter le crabe dans le groupe "ennemi" pour que l'épée puisse le toucher comme les autres ennemis.

## 7. Ajouter des dangers de bateau

Durée estimée : 40 minutes

Pour que le niveau 2 ne ressemble pas au niveau 1, nous allons ajouter des dangers liés au bateau.

Idées simples :

- des trous entre les plateformes ;
- des zones de chute dans l'eau ;
- des tonneaux ou caisses qui bloquent le passage ;
- des plateformes plus étroites ;
- des ennemis placés près du trésor.

Il faut éviter de faire un niveau trop difficile. Le but est que les enfants puissent le terminer en testant plusieurs fois.

## 8. Ajouter un mini-menu entre les niveaux

Durée estimée : 30 minutes

Pour rendre la progression plus claire, nous pouvons ajouter une petite scène entre les deux niveaux.

Nom conseillé :

- "Transition_Niveau_2"

Cette scène peut afficher :

- "Niveau 1 terminé !"
- "Direction le bateau pirate !"
- "Appuie sur Entrée pour continuer"

Le diamant du niveau 1 peut envoyer vers cette scène, puis cette scène envoie vers "Niveau_2".

Cette étape est utile pour les enfants qui ont besoin de comprendre qu'ils commencent une nouvelle partie de l'aventure.

## 9. Mettre à jour la victoire et le Game Over

Durée estimée : 40 minutes

Le jeu doit pouvoir se terminer proprement à la fin du jour 2.

À faire :

- créer ou mettre à jour la scène "Victoire" ;
- afficher le score final ;
- afficher le nombre de pièces ;
- afficher un message de fin comme "Le trésor est récupéré !" ;
- permettre de recommencer depuis le début ;
- vérifier que la scène "GameOver" fonctionne depuis le niveau 1 et le niveau 2.

À la fin du jour 2, même si l'enfant ne revient pas au jour 3, son jeu doit avoir une vraie fin.

## 10. Test complet du jeu

Durée estimée : 1 heure

Pour terminer la journée, il faut tester le jeu complet.

Parcours à tester :

- commencer au niveau 1 ;
- récupérer des pièces ;
- battre au moins un ennemi ;
- atteindre le diamant ;
- passer au niveau 2 ;
- trouver le trésor ;
- sortir du niveau 2 ;
- arriver sur la scène "Victoire".

Il faut aussi tester la défaite :

- perdre contre un ennemi ;
- tomber dans un trou ;
- vérifier que le Game Over fonctionne.

Pendant le test, chaque enfant peut ajuster son niveau 2 :

- déplacer un crabe trop difficile ;
- ajouter une potion si le niveau est trop dur ;
- déplacer le trésor s'il est trop facile ;
- ajouter quelques pièces pour guider le joueur ;
- raccourcir un passage si le niveau devient trop long.

## Planning conseillé

| Moment | Durée | Travail |
|:--|:--:|:--|
| Test du jour 1 | 20 min | Vérifier la base existante |
| Scène Niveau_2 | 45 min | Créer le décor de bateau ou de port |
| Lien niveau 1 vers niveau 2 | 35 min | Modifier l'action du diamant |
| Objectif du niveau 2 | 50 min | Ajouter le trésor et la variable `hasTreasure` |
| Sortie du niveau 2 | 40 min | Créer une sortie conditionnelle |
| Crabe ennemi | 1 h | Ajouter un nouvel ennemi pirate |
| Dangers de bateau | 40 min | Ajouter des obstacles différents |
| Transition | 30 min | Ajouter une scène entre les niveaux |
| Victoire et Game Over | 40 min | Terminer proprement le jeu |
| Test complet | 1 h | Tester et équilibrer |

Total : environ 7 heures.

## Priorités si le groupe prend du retard

À faire en priorité :

- créer le niveau 2 ;
- relier le niveau 1 au niveau 2 ;
- ajouter le trésor ;
- ajouter la sortie du niveau 2 ;
- avoir une scène "Victoire" fonctionnelle.

À faire seulement s'il reste du temps :

- ajouter la scène de transition ;
- ajouter beaucoup de décor ;
- ajouter plusieurs crabes ;
- ajouter des messages d'aide.

## Résultat attendu à la fin du jour 2

À la fin du jour 2, chaque enfant doit avoir un jeu complet en deux niveaux.

Le joueur doit pouvoir :

- commencer dans le niveau 1 ;
- finir le niveau 1 ;
- arriver dans le niveau 2 ;
- récupérer un trésor ;
- éviter ou combattre des crabes ;
- atteindre la sortie ;
- gagner le jeu.

Le jeu doit être terminé proprement à ce stade, même si un jour 3 est prévu ensuite.
