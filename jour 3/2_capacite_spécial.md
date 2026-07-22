# Capacité spécial

## un nouveau Collectible

Nous allons rajouté un nouveau objet "sprite" qui utilisera la potion bleu, il peux être créée dans la scene qu'on veux,
étant donné qu'on la transformera en objet global

![img.png](image_2/img.png)

nous allons la mettre en objet global et en disposé un peux partout dans nos différent monde

![img_1.png](image_2/img_1.png)

dans les événement, nous allons rajouté que, si on récupére cette potion, nous allons augmenté la variable global "
power". nous allons quand même mettre un cap max, afin d'évité d'avoir trop de "power".

Donc on ajoute un événement dans le groupe "collectible"

![img_2.png](image_2/img_2.png)

![img_3.png](image_2/img_3.png)

le fait d'utilisé "min()" permet de faire en sorte que ça sois la plus petite valeur entre la nouvelle valeur de power (
power + 1) et la valeur max. si on dépasse la valeur max (qui est 4) on vas bloqué a 4

on pense aussi a supprimé l'objet, afin de ne pas a le ramassé en boucle

![img_4.png](image_2/img_4.png)

Bien pensé a la copier collé dans les autre niveau

## Lancé d'épée

Nous allons créée un nouvelle objet "sprite" qu'on mettra en objet global et dedans nous allons mettre simplement l'
image présent dans le dossier "sword/23-sword embedded"

![img_5.png](image_2/img_5.png)

et nous allons modifier les point pour déplacé le point d'origine au niveau du manche de l'épée

![img_14.png](image_2/img_14.png)

maintenent nous allons géré le lancé d'épée, pour cela nous allons créée un nouvelle événement dans le groupe joueur, et
nous allons vérifier si une touche est préssé, et si on a assez de power

![img_6.png](image_2/img_6.png)

En action nous allons retiré 2 a power, et nous allons faire apparaitre l'épée qui ce lance au point du joueur "sword"

![img_7.png](image_2/img_7.png)

et nous allons rajouté deux événement en dessous de l'événement qu'on vient d'ajouté de cette façon

![img_8.png](image_2/img_8.png)

cela nous permet de mettre une sous condition, dans laquel on vas vérifier l'oriantation du joueur

![img_9.png](image_2/img_9.png)

sur le deuxième événement, nous allons faire clique droit puis remplacé et enfin "faite en une else pour événement
précédent"

![img_10.png](image_2/img_10.png)

cela vas nous donné ceci

![img_11.png](image_2/img_11.png)

et vas nous permettre de mettre des action sur l'inverse du précédent événement

sur le premièr événement, nous allons retournée l'épée lancé, puis nous allons lui appliqué une force permanante dans la
direction x negative

![img_12.png](image_2/img_12.png)

pour l'autre événement, on a juste a appliqué une force mais dans l'autre sence

![img_13.png](image_2/img_13.png)

On pence bien a mettre l'objet de l'épée dans les objets globaux et a copier collé le code dans les autre niveau

nous pouvons maintenent test que tout fonctionne avant de passé a l'étape suivante

## détéction des ennemies et disparition

On vas commencé par les ennemie, on vas rajouté un événement dans le groupe joueur dans lequel on vas mettre en
condition que l'épée lancé touche un ennemie (du groupe ennemie) cela le supprime, supprime l'épée lancé et rajoute du
score

![img_15.png](image_2/img_15.png)

![img_16.png](image_2/img_16.png)

on le copie colle dans les autre niveau

On vas mettre en place que si l'épée lancé sort de la caméra (de ce qu'on vois) alors l'épée disparais

pour cela on vas allez dans l'épée lancé puis comportement puis on ajoute les comportement "Détruire en dehors de
l'écran"

![img_18.png](image_2/img_18.png)
![img_17.png](image_2/img_17.png)

cela vas nous permettre de faire disparaitre l'épée quand elle sort de l'écrant

## Affichage du Power

Maintenent qu'on a paramettré notre power, il nous faut l'affiché sur l'hud, pour cela nous allons créée un nouvelle
objet "barre de ressource" et dedans nous allons selectionné la barre que nous souhaitons

![img_19.png](image_2/img_19.png)

puis une fois cela fait, nous faisons double clique sur la barre pour affiché c'est paramettre et nous allons mettre la
valeur initial a 0 et la valeur max a 4

![img_20.png](image_2/img_20.png)

ensuite on ajoute la barre dans l'hud, en veillant a bien selectionné le calque "HUD" (ou en metant l'objet puis dans
les propiété en selectionnant le calque "hud")
vous pouvez la placé la ou vous voulez, et vous mettez la barre dans les objets globaux afin de pouvoir la rajouté dans
tout les niveaux

une fois cela fait, nous pouvons allez dans la partie code et dans le même événement où l'on a mis en place la vie dans
la barre de vie, nous allons mettre la valeur de la barre de power a la valeur de la variable power

![img_21.png](image_2/img_21.png)
