# Personnage

## Ajout du personnage

Nous allons créer un nouvel objet. Cette fois-ci, nous allons choisir un sprite.

![img.png](image_3/img.png)

Nous allons l'appeler "joueur".

![img_1.png](image_3/img_1.png)

Nous allons ensuite ajouter toutes les animations dont nous aurons besoin pour ce personnage.

Pour le faire facilement, créez une nouvelle animation pour chaque action du personnage.

Voici ce que cela donne pour les animations de course. Il est important de les nommer comme ceci afin que ce soit plus
simple à utiliser plus tard. Il faut aussi bien cocher "en boucle".
![img_2.png](image_3/img_2.png)

Nous allons faire la même chose pour les animations de saut, d'attente (idle) et de dégât (hit).

![img_3.png](image_3/img_3.png)

## Ajout des comportements

Dans l'onglet "Comportement", nous allons ajouter ces comportements :

- Santé (avec 3 points de vie de base, 3 points de vie maximum et un damage cooldown de 1,5)
- SmoothPlatformerCamera (cela ajoute le platformerObject)
- RemapForPlatformer

![img_7.png](image_3/img_7.png)
![img_5.png](image_3/img_5.png)

![img_6.png](image_3/img_6.png)

![img_8.png](image_3/img_8.png)

![img_9.png](image_3/img_9.png)

Voici la liste de tous les comportements que vous devez avoir.

![img_12.png](image_3/img_12.png)

## Point

Il faut maintenant configurer le point où se trouvera l'épée quand le joueur attaquera.

Pour cela, cliquez sur le bouton "Modifier les points".

![img_13.png](image_3/img_13.png)

Puis ajoutez un nouveau point que nous allons appeler "sword" et placez-le à l'endroit où nous voulons que l'épée soit.

![img_14.png](image_3/img_14.png)

![img_15.png](image_3/img_15.png)

Ce point pourra être déplacé plus tard si l'épée n'est pas au bon endroit.

## Ajouter le joueur dans le monde

Maintenant, nous allons ajouter le joueur dans le monde.

En premier lieu, nous allons mettre le joueur en tant qu'objet global en faisant un clic droit dessus, puis en cliquant
sur "Définir comme objet global".

Pour cela, il suffit de glisser-déposer le joueur dans le monde, au-dessus de notre tilemap.

Maintenant, nous pouvons lancer le jeu afin de vérifier que tout fonctionne et voir s'il y a des paramètres à modifier.
![img_18.png](image_3/img_18.png)
![img_19.png](image_3/img_19.png)

Nous pouvons voir que la caméra est trop éloignée.

Pour zoomer, nous allons aller dans l'onglet "Évènement".

![img_22.png](image_3/img_22.png)

Puis nous allons créer un nouvel évènement.

![img_23.png](image_3/img_23.png)

Nous allons laisser les conditions vides afin que l'action soit toujours activée. Nous allons ensuite ajouter l'action "
zoom de la caméra" en cliquant sur le bouton "Ajouter une action".

![img_24.png](image_3/img_24.png)
![img_25.png](image_3/img_25.png)

## Jouer les bonnes animations

Maintenant, nous allons faire en sorte que, si le joueur se déplace, les bonnes animations soient jouées.

Toujours dans "Évènement", créez un groupe d'évènements en faisant un clic droit sur "Ajouter un nouvel évènement".

![img_26.png](image_3/img_26.png)

Appelez-le "Joueur".

![img_27.png](image_3/img_27.png)

Ensuite, créez trois nouveaux évènements que nous glisserons dans le dossier que nous venons de créer.

![img_28.png](image_3/img_28.png)

Dans le premier évènement, nous allons mettre comme condition que si la vitesse de déplacement est "égale à" 0, alors
nous appliquons au joueur l'animation idle.

![img_29.png](image_3/img_29.png)

Pour l'action, cliquez sur "utiliser une expression".

![img_30.png](image_3/img_30.png)

![img_31.png](image_3/img_31.png)

Dans les deux autres évènements, ce sera presque identique, mais nous vérifierons si la vitesse est supérieure à 0 ou
inférieure à 0.

![img_32.png](image_3/img_32.png)

Nous allons leur mettre comme action le changement d'animation sur "run".

Enfin, nous allons ajouter une deuxième action : le retournement du joueur.
![img_34.png](image_3/img_34.png)
![img_33.png](image_3/img_33.png)

## Détection de la mort

Quand le joueur n'a plus de vie, on vas devoir lui faire recommencé le jeux.
pour cela on vas créée un nouveau évènement dans le groupe joueur

![img_46.png](image_3/img_45.png)

Nous allons retourner dans l'onglet de scène et créer un nouveau sprite que nous appellerons "MortCollision".

![img_36.png](image_3/img_36.png)

Cette fois-ci, cliquez sur "créer avec Piskel".

Premièrement, cliquez sur le pot de peinture.
Puis choisissez la couleur que vous voulez.
Enfin, cliquez une fois sur la zone centrale.

![img_37.png](image_3/img_37.png)

Enfin, sauvegardez.

Nous allons ajouter un nouveau calque que nous appellerons "collision".

![img_38.png](image_3/img_38.png)

Sélectionnez le calque "Collision" en appuyant sur le petit bouton à côté du nom.
Il faudra faire attention à le retirer une fois que nous aurons fini les collisions.

![img_39.png](image_3/img_39.png)

Ensuite, glissez-déposez l'objet "MortCollision" dans la scène et agrandissez-le pour qu'il fasse la bonne taille.
Pour dupliquer l'élément, vous pouvez appuyer sur les touches "Ctrl + D".

![img_40.png](image_3/img_40.png)

Enfin, nous allons cacher le calque de collision et sélectionner de nouveau le "calque de base".

![img_41.png](image_3/img_41.png)

Maintenant, nous allons retourner dans l'onglet des évènements et ajouter un nouvel évènement dans le groupe "Joueur".

![img_42.png](image_3/img_42.png)

Choisissez comme condition "collision" et sélectionnez notre objet "MortCollision".

![img_43.png](image_3/img_43.png)

En action, nous allons pour l'instant recharger la scène. Plus tard, nous retirerons une vie au joueur.

![img_44.png](image_3/img_44.png)
![img_45.png](image_3/img_45.png)

Maintenant, nous pouvons tester notre jeu afin de vérifier si tout fonctionne correctement.




