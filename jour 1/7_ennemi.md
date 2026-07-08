# Ennemi

## L'étoile de mer

Nous allons ajouter un nouvel ennemi. Pour cela, nous allons créer un nouveau sprite que nous appellerons "etoile_de_mer".
![img.png](image_7/img.png)

Nous allons ajouter les sprites d'animation qui se trouvent dans le dossier "star".

![img_1.png](image_7/img_1.png)
![img_2.png](image_7/img_2.png)

Nous allons aller dans les comportements pour ajouter le comportement "Personnage se déplaçant sur des plateformes".
![img_13.png](image_7/img_13.png)
Puis nous allons désactiver "les contrôles du clavier".
![img_14.png](image_7/img_14.png)

## Action de l'ennemi

Nous allons retourner dans l'onglet des évènements afin d'ajouter les actions de l'ennemi.

Nous allons ajouter un nouveau groupe d'évènements que nous appellerons "ennemi".

![img_3.png](image_7/img_3.png)
![img_4.png](image_7/img_4.png)

Nous allons ajouter un nouvel évènement dans ce groupe.

En condition, nous allons mettre que si l'ennemi entre en collision avec le joueur, alors nous allons ajouter deux actions : retirer 1 point de vie au joueur et appliquer l'animation "attaque" à l'ennemi.

![img_5.png](image_7/img_5.png)
![img_6.png](image_7/img_6.png)
![img_7.png](image_7/img_7.png)

![img_8.png](image_7/img_8.png)

Actuellement, quand l'ennemi finit son animation, il reste sur l'animation "attaque". Nous allons donc ajouter un nouvel évènement qui fera que, si l'ennemi a fini son animation, il appliquera l'animation "idle".

![img_9.png](image_7/img_9.png)
![img_10.png](image_7/img_10.png)
![img_11.png](image_7/img_11.png)

![img_12.png](image_7/img_12.png)

## Ajouter l'ennemi dans la scène et dans le groupe

Pour que le joueur puisse interagir avec l'ennemi, nous allons ajouter l'ennemi dans la scène et dans le groupe "ennemi" que nous avons créé précédemment.
Il suffit de double-cliquer sur le groupe "ennemi".
Puis ajoutez le sprite "etoile_de_mer" dans le groupe "ennemi".
![img_15.png](image_7/img_15.png)

Maintenant, il suffit d'ajouter l'ennemi dans la scène.


## Amélioration du monde

À partir de tout ce qui a été fait précédemment, nous allons améliorer notre monde en l'agrandissant et en ajoutant les objets que nous avons créés précédemment.


