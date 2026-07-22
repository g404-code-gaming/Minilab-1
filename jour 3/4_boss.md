# Boss

## ajout de l'objet

Nous allons créée un boss qui sera un requin géant, pour cela nous allons créer un nouveau objet "Sprite" qu'on
appelera "Boss"

Toute les annimation ce trouve dans le dossier "requin"

![img.png](image_4/img.png)

nous allons lui augmenté ça taille, en cliquant sur "Option avancé"

![img_5.png](image_4/img_5.png)
puis mettre 2 en facteur de taille
![img_6.png](image_4/img_6.png)

puis en comportement nous allons lui rajouté de la vie, ainsi qu'un comportement d'objet de plateforme

![img_1.png](image_4/img_1.png)
![img_2.png](image_4/img_2.png)

![img_3.png](image_4/img_3.png)

![img_4.png](image_4/img_4.png)

nous allons ensuite lui rajouté une variable

![img_9.png](image_4/img_9.png)

qu'on appellera "Active" et qui sera en boolean (vrai ou faux) et en faux de base

![img_10.png](image_4/img_10.png)

## événement

Cette fois ci, nous allons utilisé toute les animations

en premier nous allons créée un groupe d'événement qu'on vas appeler "Boss"

![img_7.png](image_4/img_7.png)
![img_8.png](image_4/img_8.png)

et dedans nous allons y mettre des événements

Le premier événement est que, si le joueur rentre dans la zone de detection du boss, et ce une seul fois, alors on vas
changé la variable "Active" du boss a "vrai"

![img_11.png](image_4/img_11.png)
![img_12.png](image_4/img_12.png)
![img_13.png](image_4/img_13.png)

le second événement est que, si le boss est en active, et en vie, alors il vas se raproché du joueur mais uniquement sur
l'axe "x"

![img_14.png](image_4/img_14.png)
![img_27.png](image_4/img_27.png)

![img_15.png](image_4/img_15.png)

![img_16.png](image_4/img_16.png)

nous allons rajouté ensuite 2 autre événement qui permettron de retourné le boss afin qu'il regarde toujours dans la bonne direction

pour cela nous allons prendre la condition "comparer deux nombre" et comparé la différence entre la position du joueur et la position du boss, si il est positif (supérieur a 0) alors le joueur se trouve sur la droite du boss, si il est négatif (inférieur a 0) alors le joueur se trouve sur la gauche du boss
on fait ça pour les deux événement

![img_31.png](image_4/img_31.png)
![img_32.png](image_4/img_32.png)


Ensuite nous allons mettre en place les dégat du joueur
il y aura plusieurs événement lier à cela

les deux premier son pour la detection des épée sur le boss, on vérifie si l'épée rentre en collision avec le boss et si c'est le cas on retire de la vie au boss et on suprimme l'épée lancé

![img_17.png](image_4/img_17.png)
![img_18.png](image_4/img_18.png)

![img_19.png](image_4/img_19.png)

![img_20.png](image_4/img_20.png)

Nous allons rajouté 4 autre événement qui son pour les animations

Le premier est pour activé l'animation de dégat a condition que le joueur ne sois pas mort et qu'il ai pris des dégat
il faut bien activé la "condition inverse"

![img_21.png](image_4/img_21.png)

![img_22.png](image_4/img_22.png)

ensuite c'est la même chose mais si le joueur est mort, on vas jouer une autre animation

![img_23.png](image_4/img_23.png)

ensuite nous allons vérifier que l'animation est fini et que c'est l'animation "hit" et si c'est le cas, nous allons
relancé l'animation d'idle

![img_24.png](image_4/img_24.png)

et nous faisons pareil pour le dernière événement, mais avec l'animation "death"

![img_25.png](image_4/img_25.png)

voici au globale se que nous avons

![img_26.png](image_4/img_26.png)

Maintenent il ne nous reste plus qu'a faire en sorte que quand le boss attaque le joueur, que cela retire 1 point de vie
au joueur et que ça joue l'animation d'attaque

![img_28.png](image_4/img_28.png)

## fin du niveau

maintenent que le boss est mort, nous allons faire apparaitre le diamant sur lui, pour cela nous allons rajouté un
événement, dans lequel nous allons vérifier que l'animation de mort est terminé, et si c'est le cas faire apparaitre un
diamant

![img_29.png](image_4/img_29.png)

![img_30.png](image_4/img_30.png)

