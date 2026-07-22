# Jour 1 - Créer la base du jeu pirate

## Objectif de la journée

Le jour 1 sert à créer une première version jouable du jeu. Les enfants doivent repartir avec un petit jeu complet, même s'ils ne reviennent pas les jours suivants.

Pendant cette journée, nous allons créer les bases du projet dans GDevelop :

- les variables globales ;
- le rendu pixel art ;
- un premier niveau avec une tilemap ;
- un joueur qui peut se déplacer et sauter ;
- des objets à collecter ;
- une interface avec la vie, les pièces et le score ;
- une épée pour attaquer ;
- un premier ennemi ;
- une fin de niveau simple.

À la fin de la journée, le jeu doit être jouable du début à la fin.

La journée est prévue pour durer environ 7 heures.

## 1. Préparer le projet

Durée estimée : 15 minutes

Nous commençons par ouvrir le projet et vérifier que les assets sont bien disponibles.

Assets importants pour le jour 1 :

- `assets/tileset/island_tileset.png`
- `assets/joueur`
- `assets/props/Gold Coin`
- `assets/props/Red Potion`
- `assets/props/Green Diamond`
- `assets/sword`
- `assets/star`

Le but est que tout le monde parte de la même base avant de créer le jeu.

## 2. Créer les variables globales et régler le pixel art

Durée estimée : 35 minutes

Nous allons créer les variables globales qui serviront pendant tout le projet.

Variables à créer :

| Nom   |  Type  | Valeur de départ |
|:------|:------:|:----------------:|
| life  | nombre |        4         |
| coins | nombre |        0         |
| score | nombre |        0         |
| power | nombre |        0         |

Nous allons aussi activer les réglages de rendu pour que les textures pixel art restent nettes.

À faire :

- activer "Arrondir les positions des pixels" ;
- mettre la mise à l'échelle sur "au plus proche".

Ces réglages évitent que les sprites et les tiles deviennent flous.

## 3. Créer le premier niveau avec la tilemap

Durée estimée : 50 minutes

Nous allons créer le décor principal du premier niveau avec une tilemap.

Objectif :

- créer un objet "TileMap" ;
- utiliser `island_tileset.png` ;
- régler la taille des tuiles à 32 ;
- choisir quelles tuiles ont des collisions ;
- ajouter le comportement "Plateforme" ;
- placer la tilemap dans la scène.

Ensuite, chaque enfant commence à dessiner un petit niveau simple.

Le niveau doit contenir :

- un sol de départ ;
- quelques plateformes ;
- quelques trous ;
- une zone de fin ;
- assez d'espace pour placer le joueur, des pièces et un ennemi.

Le niveau n'a pas besoin d'être très grand. Il doit surtout être clair et jouable.

## 4. Ajouter le joueur

Durée estimée : 1 heure

Nous allons créer le personnage principal.

À faire :

- créer un sprite appelé "joueur" ;
- ajouter les animations d'attente, de course, de saut et de dégât ;
- mettre les animations nécessaires en boucle ;
- ajouter les comportements du joueur ;
- placer le joueur dans la scène ;
- le définir comme objet global.

Comportements importants :

- Santé ;
- SmoothPlatformerCamera ;
- RemapForPlatformer ;
- Personnage se déplaçant sur des plateformes.

Le joueur doit pouvoir se déplacer correctement dans le niveau.

## 5. Régler la caméra, les animations et la mort

Durée estimée : 45 minutes

Nous allons rendre le joueur plus lisible et plus agréable à contrôler.

À faire :

- régler le zoom de la caméra ;
- jouer l'animation "idle" quand le joueur ne bouge pas ;
- jouer l'animation "run" quand le joueur avance ;
- retourner le joueur selon sa direction ;
- créer une zone de mort appelée "MortCollision" ;
- recharger la scène si le joueur tombe dans le vide.

Cette étape permet d'avoir une première boucle de jeu : le joueur peut explorer, tomber et recommencer.

## 6. Ajouter les objets à collecter

Durée estimée : 45 minutes

Nous allons ajouter les premiers objets à récupérer.

Objets à créer :

- une pièce ;
- une potion de soin ;
- un diamant.

Rôle des objets :

- la pièce augmente `coins` et `score` ;
- la potion soigne le joueur ;
- le diamant sert de fin de niveau.

Ces objets doivent être placés dans le niveau pour guider le joueur. Les pièces peuvent montrer le chemin, la potion peut aider avant une zone dangereuse et le diamant doit être placé à la fin.

## 7. Créer l'interface du jeu

Durée estimée : 45 minutes

Nous allons créer un HUD pour afficher les informations importantes.

À afficher :

- la barre de vie ;
- le nombre de pièces ;
- le score.

Le HUD doit rester visible pendant le jeu. Il faut donc utiliser un calque HUD et placer les éléments dans un endroit facile à lire.

À la fin de cette étape, le joueur doit comprendre :

- combien de vie il lui reste ;
- combien de pièces il a récupérées ;
- combien de points il a gagnés.

## 8. Ajouter l'épée

Durée estimée : 45 minutes

Nous allons ajouter une attaque simple avec une épée.

À faire :

- créer un sprite "épée" ;
- régler son point d'origine ;
- ajouter un point "sword" sur le joueur ;
- faire apparaître l'épée quand le joueur appuie sur une touche ;
- supprimer l'épée quand son animation est terminée ;
- faire suivre l'épée avec le joueur ;
- retourner l'épée quand le joueur change de direction.

L'épée sert à préparer le combat contre les ennemis.

## 9. Ajouter le premier ennemi

Durée estimée : 40 minutes

Nous allons ajouter un premier ennemi : l'étoile de mer.

À faire :

- créer un sprite "etoile_de_mer" ;
- ajouter ses animations ;
- ajouter le comportement de plateforme ;
- désactiver les contrôles du clavier ;
- créer un groupe "ennemi" ;
- ajouter l'étoile de mer dans ce groupe.

Logique de combat :

- si l'ennemi touche le joueur, le joueur perd de la vie ;
- si l'épée touche l'ennemi, l'ennemi disparaît ;
- le score augmente quand l'ennemi est battu.

Cette étape donne un vrai danger au niveau.

## 10. Test final et amélioration du monde

Durée estimée : 40 minutes

Pour terminer la journée, chaque enfant teste son jeu du début à la fin.

À tester :

- le joueur peut traverser le niveau ;
- les plateformes fonctionnent ;
- les trous font recommencer ;
- les pièces augmentent le compteur ;
- les potions soignent ;
- l'épée fonctionne ;
- l'ennemi peut blesser le joueur ;
- l'ennemi peut être battu ;
- le diamant termine le niveau.

Ensuite, chacun peut améliorer son niveau.

Améliorations possibles :

- ajouter quelques plateformes ;
- déplacer les pièces pour mieux guider le joueur ;
- placer une potion avant l'ennemi ;
- ajuster la position du diamant ;
- rendre le niveau plus joli avec la tilemap.

## Planning conseillé

| Moment                     | Durée  | Travail                                         |
|:---------------------------|:------:|:------------------------------------------------|
| Préparation                | 15 min | Ouvrir le projet et vérifier les assets         |
| Variables et pixel art     | 35 min | Créer les variables globales et régler le rendu |
| Tilemap                    | 50 min | Créer le premier niveau                         |
| Joueur                     |  1 h   | Ajouter le personnage et ses comportements      |
| Caméra, animations et mort | 45 min | Rendre le joueur jouable et lisible             |
| Objets à collecter         | 45 min | Ajouter pièce, potion et diamant                |
| HUD                        | 45 min | Afficher vie, pièces et score                   |
| Épée                       | 45 min | Ajouter l'attaque du joueur                     |
| Ennemi                     | 40 min | Ajouter l'étoile de mer et le combat            |
| Test final                 | 40 min | Tester et améliorer le niveau                   |

Total : environ 7 heures.

## Priorités si le groupe prend du retard

À faire en priorité :

- créer les variables globales ;
- créer le premier niveau ;
- ajouter le joueur ;
- ajouter les pièces ;
- afficher la vie et le score ;
- ajouter une fin de niveau avec le diamant.

À faire seulement s'il reste du temps :

- ajouter l'épée ;
- ajouter l'ennemi ;
- améliorer le décor ;
- ajouter plus d'objets à collecter.

## Résultat attendu à la fin du jour 1

À la fin du jour 1, chaque enfant doit avoir un premier jeu jouable.

Le joueur doit pouvoir :

- se déplacer dans un niveau ;
- sauter sur des plateformes ;
- récupérer des pièces ;
- voir sa vie et son score ;
- se soigner avec une potion ;
- attaquer avec une épée ;
- combattre un ennemi ;
- atteindre un diamant pour terminer le niveau.

Le jeu doit être simple, mais complet. Si un enfant ne revient pas les jours suivants, il aura quand même créé une vraie première version de son jeu.
