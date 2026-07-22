# Jour 3 - Mécaniques avancées, îles pirates et boss final

## Objectif de la journée

Le jour 1 a permis de créer la base du jeu. Le jour 2 a ajouté un deuxième niveau pirate, un trésor, un nouvel ennemi et une progression plus claire.

Le jour 3 sert à transformer le projet en une vraie petite aventure d'action, plus orientée mécanique. L'objectif n'est pas seulement d'ajouter une grande carte, mais d'ajouter des systèmes de jeu que le joueur peut comprendre, utiliser et améliorer.

À la fin de la journée, le jeu devra contenir :

- trois niveaux jouables ;
- une carte finale qui mélange bateau pirate et petites îles ;
- un pouvoir permettant de lancer son épée en ligne droite ;
- un chronomètre global pour créer un mode speedrun ;
- un boss final avec plusieurs points de vie ;
- une sortie finale qui s'ouvre après le boss ;
- quelques raccourcis ou bonus pour donner envie de rejouer ;
- une vraie scène de victoire avec score et temps final.

La journée est prévue pour durer environ 7 heures.

## Ce que nous gardons des jours 1 et 2

Nous gardons toute la base déjà construite :

- le niveau 1 ;
- le niveau 2 ;
- le joueur ;
- les pièces ;
- les potions ;
- les ennemis ;
- l'épée ;
- la vie ;
- le score ;
- le trésor du niveau 2 ;
- les scènes de victoire et de défaite.

Le jour 3 ajoute des mécaniques par-dessus cette base. Il ne doit pas casser ce qui fonctionne déjà.

## 1. Test rapide du jeu en deux niveaux

Durée estimée : 20 minutes

Avant d'ajouter la suite, nous testons rapidement le jeu du jour 2.

À vérifier :

- le niveau 1 mène bien au niveau 2 ;
- le niveau 2 demande bien de récupérer le trésor ;
- le crabe fonctionne ;
- l'épée touche correctement les ennemis ;
- la victoire du jour 2 fonctionne ;
- le Game Over fonctionne dans les deux niveaux ;
- les variables globales `life`, `coins`, `score` et `power` sont conservées.

Si tout fonctionne, nous pouvons transformer la victoire du jour 2 en passage vers le jour 3.

## 2. Créer la carte finale bateau + îles

Durée estimée : 40 minutes

Nous allons créer une nouvelle scène pour le dernier niveau.

Nom conseillé :

- "Niveau_3"

Le niveau 3 doit mélanger deux ambiances :

- une partie bateau pirate avec un pont, des caisses, des mâts et des trous ;
- une partie îles avec de petites plateformes, de l'eau, des palmiers ou des rochers ;
- une zone finale plus fermée pour le boss.

Structure conseillée :

- départ sur le bateau ;
- premier combat simple ;
- saut vers une petite île ;
- passage avec plateformes ou trous d'eau ;
- retour sur une partie de bateau cassé ;
- zone de repos avec une potion ;
- arène du boss ;
- sortie finale après le boss.

Le niveau doit être assez long pour occuper la journée, mais il doit rester testable. Il vaut mieux une carte moyenne avec de bonnes mécaniques qu'une carte immense et vide.

## 3. Relier le niveau 2 au niveau 3

Durée estimée : 20 minutes

Au jour 2, la sortie du niveau 2 envoyait vers la scène "Victoire".

Pour le jour 3, nous allons changer cette logique :

- si le joueur termine le niveau 2, il va vers une scène de transition ;
- la transition annonce la dernière zone ;
- puis le joueur arrive dans "Niveau_3".

Nom conseillé pour la transition :

- "Transition_Final"

Texte possible :

- "La carte mène vers l'île du capitaine..."
- "Dernière épreuve : le repaire pirate"
- "Appuie sur Entrée pour continuer"

La scène "Victoire" sera gardée pour la vraie fin du jeu.

## 4. Ajouter le chronomètre global de speedrun

Durée estimée : 35 minutes

Nous allons ajouter un chronomètre global. Il commence au début du niveau 1 et continue jusqu'à la victoire finale.

Nouvelle variable globale conseillée :

| Nom | Type | Valeur de départ |
|:--|:--:|:--:|
| globalTime | nombre | 0 |

Logique :

- au lancement du niveau 1, mettre `globalTime` à 0 ;
- pendant le jeu, ajouter le temps écoulé à `globalTime` ;
- ne pas remettre `globalTime` à 0 quand le joueur passe au niveau 2 ou au niveau 3 ;
- afficher le temps dans le HUD ;
- afficher le temps final dans la scène "Victoire".

Texte HUD conseillé :

- "Temps : 0.00"

Objectif pédagogique :

- comprendre qu'une variable globale peut suivre toute la partie ;
- créer un système qui donne envie de rejouer pour aller plus vite.

## 5. Afficher un objectif de speedrun

Durée estimée : 20 minutes

Pour que le chrono serve vraiment, nous ajoutons des objectifs de temps.

Exemple de grades :

| Temps final | Grade |
|:--|:--|
| moins de 3 minutes | Capitaine éclair |
| moins de 5 minutes | Pirate rapide |
| moins de 7 minutes | Marin efficace |
| 7 minutes ou plus | Explorateur tranquille |

À faire :

- afficher le temps final dans la scène "Victoire" ;
- afficher un grade selon le temps ;
- garder aussi le score final ;
- expliquer que le joueur peut refaire le jeu pour améliorer son temps.

Option si le groupe avance vite :

- ajouter une variable globale `bestTime` ;
- si le nouveau temps est meilleur, afficher "Nouveau record !"

## 6. Créer le pouvoir : lancer l'épée en ligne droite

Durée estimée : 1 heure

La variable globale `power` existe déjà depuis le jour 1. Nous allons l'utiliser pour créer un vrai pouvoir.

Idée principale :

- le joueur charge son pouvoir ;
- quand `power` atteint 3, il peut lancer son épée ;
- l'épée part en ligne droite devant le joueur ;
- elle touche les ennemis à distance ;
- après utilisation, `power` revient à 0.

Touche conseillée :

- "E" pour lancer l'épée.

Objet conseillé :

- créer un objet "EpeeProjectile" ou réutiliser l'image de l'épée avec une taille adaptée.

Variables utiles :

| Nom            |      Type      | Utilité                                    |
|:---------------|:--------------:|:-------------------------------------------|
| power          |    globale     | savoir si le pouvoir est chargé            |
| swordDirection | objet ou scène | savoir si l'épée part à droite ou à gauche |
| swordSpeed     |     nombre     | vitesse du projectile                      |

Règles simples conseillées :

- récupérer une pièce spéciale donne +1 à `power` ;
- `power` ne peut pas dépasser 3 ;
- si `power` vaut 3 et que le joueur appuie sur "E", créer l'épée projectile ;
- l'épée projectile avance en ligne droite ;
- si elle touche un ennemi, l'ennemi disparaît ou perd de la vie ;
- si elle touche un mur ou sort de l'écran, elle disparaît ;
- après le lancer, `power` revient à 0.

Cette mécanique doit être claire visuellement. Le joueur doit comprendre qu'il peut attaquer à distance, mais seulement quand le pouvoir est chargé.

## 7. Afficher la jauge de pouvoir

Durée estimée : 25 minutes

Comme le joueur peut maintenant utiliser un pouvoir, il faut l'afficher à l'écran.

À faire :

- ajouter un texte dans le HUD ;
- afficher "Pouvoir : 0 / 3" au début ;
- mettre à jour le texte avec la variable globale `power` ;
- placer ce texte près du score, de la vie et du chrono.

Option plus visuelle :

- afficher 3 petites icônes ;
- une icône visible par point de pouvoir ;
- quand les 3 icônes sont allumées, le joueur sait qu'il peut lancer l'épée.

Message possible quand le pouvoir est prêt :

- "Épée chargée !"

Il faut éviter un HUD trop rempli. Le chrono, la vie, le score et le pouvoir doivent rester lisibles.

## 8. Ajouter des cristaux de pouvoir et des choix de route

Durée estimée : 25 minutes

Pour rendre le pouvoir intéressant, nous ajoutons des objets qui servent à le charger.

Objet conseillé :

- "CristalPouvoir"

Logique :

- quand le joueur touche un cristal, `power` augmente de 1 ;
- le cristal disparaît ;
- le score augmente un peu ;
- si `power` est déjà à 3, le cristal peut seulement donner du score.

Placement conseillé :

- un cristal avant un groupe d'ennemis ;
- un cristal dans une zone un peu risquée ;
- un cristal juste avant le boss ;
- un cristal dans un raccourci optionnel.

Cela crée un choix :

- prendre le chemin facile mais plus long ;
- prendre le chemin dangereux pour charger le pouvoir plus vite ;
- garder le pouvoir pour le boss au lieu de l'utiliser sur les ennemis.

## 9. Ajouter des obstacles mécaniques dans la carte finale

Durée estimée : 35 minutes

Le niveau 3 doit être plus mécanique que les autres niveaux. Nous ajoutons donc quelques systèmes simples.

Idées possibles :

- un levier qui ouvre une porte ;
- une plateforme mobile entre deux îles ;
- une zone d'eau qui renvoie au dernier point de départ ;
- un pont qui apparaît après avoir récupéré un cristal ;
- des tonneaux qui bloquent le passage et peuvent être détruits avec l'épée lancée ;
- un raccourci qui s'ouvre seulement si le joueur utilise bien son pouvoir.

Choix conseillé pour la journée :

- créer au moins un levier ;
- créer au moins une porte ;
- créer un raccourci optionnel pour le speedrun.

Exemple de logique :

- si le joueur touche le levier, la variable `doorOpen` devient `true` ;
- si `doorOpen` est `true`, la porte disparaît ;
- le raccourci permet de gagner du temps, mais il demande un saut plus difficile ou un ennemi à éviter.

Cette étape rend la carte plus vivante et donne un vrai intérêt au chronomètre.

## 10. Créer le boss final

Durée estimée : 50 minutes

Nous allons créer un boss de fin simple, placé dans une arène à la fin du niveau 3.

Nom conseillé :

- "BossCapitaine" ou "BossCrabe"

Comme nous n'avons pas forcément un sprite de capitaine pirate, nous pouvons utiliser un ennemi existant en version plus grande.

Variable d'objet conseillée :

| Objet | Variable | Valeur |
|:--|:--|:--:|
| BossCapitaine | life | 6 |

Logique :

- si l'épée normale touche le boss, sa vie baisse de 1 ;
- si l'épée lancée touche le boss, sa vie baisse de 2 ;
- si le joueur touche le boss, il perd 1 point de vie ;
- si la vie du boss arrive à 0, le boss disparaît ;
- quand le boss disparaît, la sortie finale apparaît ou devient utilisable.

Pour rendre le combat plus intéressant :

- placer deux cristaux de pouvoir dans l'arène ;
- ajouter une potion avant le boss ;
- faire bouger le boss lentement de gauche à droite ;
- fermer la sortie tant que le boss est vivant.

Le boss doit être impressionnant, mais pas trop compliqué. Le plus important est que les enfants comprennent la logique de points de vie et l'intérêt de l'épée lancée.

## 11. Créer la sortie finale

Durée estimée : 20 minutes

Après le boss, le joueur doit atteindre une vraie fin.

Idées de sortie finale :

- un coffre pirate ;
- un drapeau ;
- une porte de cabine ;
- un diamant final ;
- une zone invisible appelée "SortieFinale".

La sortie finale doit fonctionner seulement si le boss est battu.

Logique :

- si le boss est encore vivant, la sortie ne fait rien ;
- si le boss est battu, toucher la sortie envoie vers la scène "Victoire".

La scène "Victoire" doit maintenant représenter la fin complète du jeu, avec le score et le temps final.

## 12. Améliorer la victoire finale

Durée estimée : 25 minutes

La scène de victoire devient la vraie fin de l'aventure.

À afficher :

- "Bravo, tu as vaincu le capitaine pirate !"
- le score final ;
- le nombre de pièces ;
- le temps final ;
- le grade de speedrun ;
- une instruction pour recommencer.

Option intéressante :

- afficher aussi un grade selon le score.

Exemple :

- moins de 1000 points : "Mousse débutant"
- entre 1000 et 2500 points : "Pirate confirmé"
- plus de 2500 points : "Capitaine du trésor"

Le joueur peut donc avoir deux objectifs :

- finir le jeu rapidement ;
- faire un gros score.

## 13. Polish et équilibrage

Durée estimée : 25 minutes

Le polish, ce sont les petits détails qui rendent le jeu plus agréable.

Idées possibles :

- ajouter un son quand le joueur lance l'épée ;
- ajouter un effet quand le pouvoir est prêt ;
- ajouter un son quand le boss prend des dégâts ;
- ajouter un message court avant le boss ;
- ajouter des pièces pour guider le bon chemin ;
- ajouter une potion avant un passage difficile ;
- vérifier que les raccourcis ne cassent pas la progression ;
- vérifier que le chrono reste lisible dans chaque niveau ;
- ajuster la vitesse de l'épée lancée ;
- ajuster la vie du boss si le combat est trop long ou trop court.

Chaque enfant peut choisir deux ou trois améliorations selon son avancement.

## 14. Test final et défi speedrun

Durée estimée : 20 minutes

Pour finir le projet, il faut tester le jeu complet du début à la fin.

Parcours à tester :

- démarrer le jeu ;
- finir le niveau 1 ;
- finir le niveau 2 ;
- atteindre le niveau 3 ;
- charger le pouvoir ;
- lancer l'épée en ligne droite ;
- utiliser ou éviter un raccourci ;
- battre le boss ;
- atteindre la vraie victoire ;
- vérifier le temps final.

À vérifier :

- le joueur ne reste jamais bloqué ;
- les scènes s'enchaînent dans le bon ordre ;
- le Game Over fonctionne ;
- le score reste cohérent ;
- le chrono ne revient pas à 0 entre les niveaux ;
- le pouvoir revient bien à 0 après utilisation ;
- l'épée projectile disparaît correctement ;
- le boss peut être battu ;
- la victoire finale affiche le score, le temps et le grade.

Pour terminer, chaque enfant peut faire un essai speedrun :

- premier essai : finir le jeu normalement ;
- deuxième essai : essayer d'aller plus vite ;
- troisième essai : tenter un raccourci ou économiser le pouvoir pour le boss.

Cette dernière partie permet de tester le jeu en conditions réelles et de voir si les mécaniques donnent envie de rejouer.

## Planning conseillé

| Moment | Durée | Travail |
|:--|:--:|:--|
| Test du jeu en deux niveaux | 20 min | Vérifier la base du jour 2 |
| Carte finale bateau + îles | 40 min | Créer le niveau 3 |
| Lien niveau 2 vers niveau 3 | 20 min | Ajouter la transition finale |
| Chronomètre global | 35 min | Créer le système de speedrun |
| Objectifs de temps | 20 min | Ajouter grades et temps final |
| Épée lancée | 1 h | Créer le pouvoir principal |
| HUD du pouvoir | 25 min | Afficher la jauge de pouvoir |
| Cristaux et choix de route | 25 min | Charger le pouvoir et créer des choix |
| Obstacles mécaniques | 35 min | Ajouter levier, porte et raccourci |
| Boss final | 50 min | Créer le combat final |
| Sortie finale | 20 min | Ouvrir la fin après le boss |
| Victoire finale | 25 min | Afficher score, temps et grades |
| Polish et équilibrage | 25 min | Ajuster sons, effets et difficulté |
| Test speedrun | 20 min | Tester le jeu complet |

Total : environ 7 heures.

## Priorités si le groupe prend du retard

À faire en priorité :

- créer le niveau 3 bateau + îles ;
- relier le niveau 2 au niveau 3 ;
- créer le chronomètre global ;
- créer l'épée lancée ;
- créer le boss ;
- permettre de battre le boss ;
- afficher la vraie victoire finale.

À faire seulement s'il reste du temps :

- ajouter les grades de speedrun ;
- ajouter le meilleur temps ;
- ajouter plusieurs raccourcis ;
- ajouter beaucoup de décoration ;
- ajouter des sons et effets supplémentaires ;
- équilibrer finement les temps des grades.

## Résultat attendu à la fin du jour 3

À la fin du jour 3, chaque enfant doit avoir une petite aventure pirate complète et rejouable.

Le joueur doit pouvoir :

- traverser trois niveaux ;
- passer d'un bateau à des îles ;
- récupérer des pièces, des potions, des trésors et des cristaux de pouvoir ;
- charger un pouvoir ;
- lancer son épée en ligne droite ;
- utiliser ce pouvoir contre des ennemis ou contre le boss ;
- chercher des raccourcis pour gagner du temps ;
- battre un boss final ;
- obtenir une vraie fin avec son score, son temps et son grade.

Le projet doit être jouable du début à la fin, mais aussi donner envie d'être rejoué pour améliorer son temps.
