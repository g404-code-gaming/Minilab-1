# HUD

## Création du calque HUD

Afin de voir la vie et le nombre de pièces collectées, nous allons créer un calque HUD.

![img.png](image_5/img.png)
![img_1.png](image_5/img_1.png)
Sélectionnez ensuite le calque HUD.

![img_4.png](image_5/img_4.png)

## Ajout de la barre de vie

Nous allons d'abord ajouter la barre de vie.

Pour cela, ajoutez un objet "Barre de ressource".

![img_2.png](image_5/img_2.png)

Sélectionnez l'une des barres que vous souhaitez utiliser. Je recommande une barre simple et rouge.

![img_3.png](image_5/img_3.png)

Puis glissez l'objet sur la scène, à l'endroit où vous souhaitez afficher la barre de vie.
Pour la placer correctement, vous pouvez dézoomer la scène et afficher le cadre de la scène.
![img_5.png](image_5/img_5.png)

Une fois cela fait, allez dans l'onglet des évènements et ajoutez un nouvel évènement que nous allons glisser au même niveau que notre autre évènement vide.

![img_6.png](image_5/img_6.png)

Nous ne mettons aucune condition. En action, nous allons modifier la valeur maximale de la barre de vie pour qu'elle soit égale à la variable globale "life".
![img_7.png](image_5/img_7.png)

Nous allons ajouter une deuxième action : modifier la valeur de la barre de vie pour qu'elle soit égale à celle du joueur.
![img_8.png](image_5/img_8.png)

![img_9.png](image_5/img_9.png)

## Ajout du compteur de pièces

Nous allons ajouter un compteur de pièces. Pour cela, ajoutez un objet "Texte" dans lequel nous écrirons "pièces : 0", puis placez-le à côté de la barre de vie.

![img_10.png](image_5/img_10.png)
![img_11.png](image_5/img_11.png)

Dans les évènements, ajoutez un nouvel évènement que nous allons glisser au même niveau que notre autre évènement vide.

![img_12.png](image_5/img_12.png)

Nous ne mettons aucune condition. En action, nous allons modifier le texte pour qu'il soit égal à "pièces : " + la variable globale "coins".
![img_13.png](image_5/img_13.png)

Nous allons aussi ajouter, quand le joueur tombe dans le vide et quand il récupère un diamant, que le compteur de coins et le score soient remis à 0.

![img_14.png](image_5/img_14.png)
![img_15.png](image_5/img_15.png)

## Affichage du score

En faisant la même chose que pour le compteur de pièces, nous allons ajouter un compteur de score. Pour cela, ajoutez un objet "Texte" dans lequel nous écrirons "score : 0", puis placez-le à côté du compteur de pièces.

![img_17.png](image_5/img_17.png)
![img_16.png](image_5/img_16.png)

## Finalité

Pour finir cette partie, nous allons mettre les objets que nous avons créés en tant qu'objets globaux, afin de pouvoir les utiliser dans toutes les scènes du jeu.


![img_18.png](image_5/img_18.png)
![img_19.png](image_5/img_19.png)


