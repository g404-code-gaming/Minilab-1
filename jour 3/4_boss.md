# Boss

## Ajout de l'objet

Nous allons créer un boss qui sera un requin géant. Pour cela, nous allons créer un nouvel objet `Sprite` que nous appellerons `Boss`.

Toutes les animations se trouvent dans le dossier `requin`.

![img.png](image_4/img.png)

Nous allons augmenter sa taille en cliquant sur `Options avancées`.

![img_5.png](image_4/img_5.png)

Puis nous mettons `2` comme facteur de taille.

![img_6.png](image_4/img_6.png)

Dans les comportements, nous allons lui ajouter de la vie, ainsi qu'un comportement d'objet de plateforme.

![img_1.png](image_4/img_1.png)
![img_2.png](image_4/img_2.png)

![img_3.png](image_4/img_3.png)

![img_4.png](image_4/img_4.png)

Nous allons ensuite lui ajouter une variable.

![img_9.png](image_4/img_9.png)

Cette variable s'appellera `Active`. Elle sera de type booléen, c'est-à-dire vrai ou faux, et elle sera à `false` par défaut.

![img_10.png](image_4/img_10.png)

## Événements

Cette fois-ci, nous allons utiliser toutes les animations.

Nous allons d'abord créer un groupe d'événements que nous appellerons `Boss`.

![img_7.png](image_4/img_7.png)
![img_8.png](image_4/img_8.png)

Nous allons ensuite y placer les événements du boss.

Le premier événement vérifie si le joueur entre dans la zone de détection du boss, une seule fois. Si c'est le cas, on met la variable `Active` du boss à `true`.

![img_11.png](image_4/img_11.png)
![img_12.png](image_4/img_12.png)
![img_13.png](image_4/img_13.png)

Le deuxième événement vérifie si le boss est actif et encore en vie. Si c'est le cas, il se rapproche du joueur, mais uniquement sur l'axe X.

![img_14.png](image_4/img_14.png)
![img_27.png](image_4/img_27.png)

![img_15.png](image_4/img_15.png)

![img_16.png](image_4/img_16.png)

Nous allons ensuite ajouter deux autres événements qui permettent de retourner le boss afin qu'il regarde toujours dans la bonne direction.

Pour cela, nous utilisons la condition `Comparer deux nombres` et nous comparons la différence entre la position du joueur et la position du boss. Si le résultat est positif, le joueur se trouve à droite du boss. S'il est négatif, le joueur se trouve à gauche du boss.

On crée cette logique dans les deux événements.

![img_31.png](image_4/img_31.png)
![img_32.png](image_4/img_32.png)

Ensuite, nous allons mettre en place les dégâts infligés au boss. Il y aura plusieurs événements liés à cela.

Les deux premiers servent à détecter les épées qui touchent le boss. On vérifie si l'épée entre en collision avec le boss. Si c'est le cas, on retire de la vie au boss et on supprime l'épée lancée.

![img_17.png](image_4/img_17.png)
![img_18.png](image_4/img_18.png)

![img_19.png](image_4/img_19.png)

![img_20.png](image_4/img_20.png)

Nous allons ajouter quatre autres événements pour gérer les animations.

Le premier sert à activer l'animation de dégâts, à condition que le boss ne soit pas mort et qu'il ait pris des dégâts. Il faut bien activer la condition inverse.

![img_21.png](image_4/img_21.png)

![img_22.png](image_4/img_22.png)

Ensuite, nous faisons la même chose pour le cas où le boss est mort : on joue une autre animation.

![img_23.png](image_4/img_23.png)

Nous allons ensuite vérifier que l'animation est terminée et qu'il s'agit de l'animation `hit`. Si c'est le cas, nous relançons l'animation `idle`.

![img_24.png](image_4/img_24.png)

Nous faisons la même chose pour le dernier événement, mais avec l'animation `death`.

![img_25.png](image_4/img_25.png)

Voici l'ensemble des événements obtenus.

![img_26.png](image_4/img_26.png)

Maintenant, il ne reste plus qu'à faire en sorte que l'attaque du boss retire 1 point de vie au joueur et joue l'animation d'attaque.

![img_28.png](image_4/img_28.png)

## Fin du niveau

Maintenant que le boss peut mourir, nous allons faire apparaître le diamant sur lui. Pour cela, nous ajoutons un événement dans lequel nous vérifions que l'animation de mort est terminée. Si c'est le cas, nous faisons apparaître un diamant.

![img_29.png](image_4/img_29.png)

![img_30.png](image_4/img_30.png)
