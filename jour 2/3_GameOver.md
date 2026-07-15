# GameOver

## De nouvelles scènes

Maintenant que nous avons un deuxième niveau, il est important d'avoir un affichage quand nous mourons et quand nous
réussissons le jeu.

Pour cela, nous allons créer une nouvelle scène que nous allons appeler "GameOver".

![img.png](image_3/img.png)
![img_1.png](image_3/img_1.png)
![img_2.png](image_3/img_2.png)

Pour avoir accès à la nouvelle scène, nous avons juste à faire un clic gauche sur la scène nouvellement créée, et cela nous
l'ouvre sur le côté.

![img_3.png](image_3/img_3.png)

Premièrement, nous allons mettre un fond un peu plus sombre. Pour cela, nous allons aller dans les calques et nous allons
changer la couleur d'arrière-plan.
![img_4.png](image_3/img_4.png)

![img_5.png](image_3/img_5.png)

Une fois cela fait, nous allons ajouter un nouvel objet de type "Texte".

![img_6.png](image_3/img_6.png)

En nom de l'objet, nous allons mettre "Titre", et nous allons changer la taille et la couleur du texte.

![img_7.png](image_3/img_7.png)

Vous pouvez le personnaliser comme vous le souhaitez.

Pour le texte à afficher, nous allons mettre "GameOver".
![img_8.png](image_3/img_8.png)

Ensuite, nous allons cliquer sur "choisir une police", puis sur "Choisissez dans le magasin de ressources".

![img_9.png](image_3/img_9.png)

Puis choisissez la police qui vous intéresse.

Une fois la personnalisation finie, nous pouvons appliquer les changements et glisser notre titre dans la scène.

![img_10.png](image_3/img_10.png)

Nous allons également afficher le score total que le joueur a gagné sur sa partie avant de perdre.
Pour cela, nous allons faire un deuxième objet "Texte" que nous allons appeler "Score_total" et nous allons écrire
dedans "Votre score : 0".

Comme précédemment, vous pouvez personnaliser le texte comme vous le souhaitez.

![img_11.png](image_3/img_11.png)

Puis nous allons le glisser dans la scène.

![img_12.png](image_3/img_12.png)

Enfin, nous allons ajouter un objet "Bouton étiqueté".

![img_13.png](image_3/img_13.png)

Et choisir le bouton qui nous plaît.

Une fois cela fait, nous avons juste à l'ajouter dans la scène et à double-cliquer dessus.

![img_14.png](image_3/img_14.png)

Dans la zone de texte "label", nous allons mettre "Recommencer".

![img_15.png](image_3/img_15.png)

## Les événements

Maintenant que notre scène a été mise en place, nous allons ajouter les événements liés à cette scène.

Nous allons cliquer sur l'onglet des événements liés à notre scène.

![img_16.png](image_3/img_16.png)

Nous allons ajouter 2 nouveaux événements.

![img_17.png](image_3/img_17.png)

Dans le premier, nous allons mettre comme condition "au lancement de la scène".
![img_18.png](image_3/img_18.png)

Puis, comme action, nous allons définir le texte du score à ["Votre score : " + score].

![img_19.png](image_3/img_19.png)
![img_20.png](image_3/img_20.png)

Sur le deuxième événement, nous allons ajouter comme condition que si le bouton est cliqué.

![img_21.png](image_3/img_21.png)

Nous allons retourner sur la scène niveau 1, en remettant le score et les pièces à 0 et la vie à 4.

![img_22.png](image_3/img_22.png)

![img_23.png](image_3/img_23.png)
![img_24.png](image_3/img_24.png)

## Scène de victoire

Maintenant, nous allons retourner là où nous avons la liste de toutes nos scènes.

![img_25.png](image_3/img_25.png)

Et nous allons faire un clic droit sur "GameOver", puis cliquer sur "Dupliquer".

![img_26.png](image_3/img_26.png)

Et nous allons l'appeler "Victoire".

![img_27.png](image_3/img_27.png)
S'il y a besoin de la renommer, il suffit de faire un clic droit sur la scène, puis de cliquer sur "Renommer".

![img_28.png](image_3/img_28.png)

Une fois cela fait, nous allons ouvrir la scène en faisant un clic gauche dessus.

![img_29.png](image_3/img_29.png)

Ensuite, nous allons double-cliquer sur l'objet de scène "Titre" pour changer le texte écrit en "Félicitation". Vous pouvez
mettre le texte que vous souhaitez, il remplacera le "GameOver".

![img_30.png](image_3/img_30.png)

![img_31.png](image_3/img_31.png)
