# Épée

## Ajout de l'épée

Pour ajouter l'épée, nous allons créer un nouveau sprite que nous appellerons "épée".

![img.png](image_6/img.png)
![img_1.png](image_6/img_1.png)

Nous allons modifier le point d'origine de l'épée pour qu'elle apparaisse au bon endroit.
Pour cela, retournez dans "Modifier les points", sélectionnez le point "origine" de l'épée, puis placez-le à l'endroit où nous voulons que l'épée soit.

![img_2.png](image_6/img_2.png)
![img_3.png](image_6/img_3.png)

Pour éviter tout problème, nous allons directement placer l'objet épée dans les objets globaux.

![img_4.png](image_6/img_4.png)

## Ajout d'un groupe ennemi

Pour la suite, nous allons ajouter tout de suite un groupe ennemi.
Pour cela, cliquez sur le bouton plus "Ajouter un groupe", puis appelez-le "ennemi".
![img_5.png](image_6/img_5.png)

![img_6.png](image_6/img_6.png)

Puis mettez-le en tant que groupe global.

![img_7.png](image_6/img_7.png)

## Action de l'épée

Nous allons aller dans l'onglet des évènements de l'épée et ajouter un nouvel évènement que nous allons glisser dans le groupe "Joueur".

![img_8.png](image_6/img_8.png)

Nous allons mettre comme condition que si le joueur appuie sur une touche, dans mon cas la touche "F", cela déclenche l'attaque. Vous pouvez choisir la touche que vous voulez, mais je vous conseille de choisir une touche facile d'accès pour le joueur.

![img_9.png](image_6/img_9.png)

En action, nous allons créer un objet "épée" et le placer au point "sword" que nous avons créé auparavant.
![img_10.png](image_6/img_10.png)

Nous allons maintenant ajouter un nouvel évènement dans le groupe "Joueur".
Cet évènement fera que, si l'objet "épée" a fini son animation, il sera supprimé.

![img_11.png](image_6/img_11.png)
![img_12.png](image_6/img_12.png)

Enfin, nous allons ajouter un dernier évènement. Si l'objet "épée" touche un objet du groupe "ennemi", l'ennemi sera supprimé et nous ajouterons 150 à la variable globale "score".

![img_13.png](image_6/img_13.png)
![img_14.png](image_6/img_14.png)
![img_15.png](image_6/img_15.png)

Voici à quoi cela ressemble.

![img_16.png](image_6/img_16.png)

Afin que notre épée suive le joueur, nous allons ajouter un dernier évènement sans condition. Il fera que, si l'objet "épée" existe, il sera placé au point "sword" du joueur.
![img_17.png](image_6/img_17.png)

Dans les évènements de déplacement du joueur, nous allons ajouter une action qui fera que si le joueur se retourne, l'objet "épée" se retourne aussi.
![img_18.png](image_6/img_18.png)
