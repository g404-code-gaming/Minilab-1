# reprise

## Vérification du jeux

La première étape de la journée est de vérifier que tout fonctionne correctement.

cette étape est importante car, après deux jour de développement, on peux se rendre compte que quelque fonctionnalité ne
fonctionne plus, ou qu'on souhaiterais modifier quelque éléments.

## Chronomettre

On vas créée un chronomettre afin de pouvoir faire du "speedrun" du jeux.

pour cela on vas créée une nouvelle variable globale,

![img.png](image_1/img.png)

| Nom        |  Type  | Valeur de départ |
|:-----------|:------:|:----------------:|
| globalTime | nombre |        0         |

![img_1.png](image_1/img_1.png)

puis on applique.

ce qu'on vas faire ces rajouté un nouvelle événement avec une condition vide, et en action on vas ajouté a la variable "
globaleTime" le temps qui c'est écoulé depuis la dernier mise a jour du jeux
Nous allons aussi rajouté juste avant l'action qu'on met a 0 la variable "globalTime" mais uniquemnet au niveau 1, afin
de remettre a jour le timer correctement.
![img_2.png](image_1/img_2.png)

on met également cette événement dans le niveau 2, mais sans la partie ou l'on remet a 0 le timer

![img_8.png](image_1/img_8.png)

![img_4.png](image_1/img_4.png)

Nous allons créée un nouvelle Objet "texte" afin d'affiché dedans le timer, cette objet peux être réalisé dans n'importe
quel scène étant donné qu'il sera ensuite mis en objet globale

![img_5.png](image_1/img_5.png)

![img_6.png](image_1/img_6.png)

![img_7.png](image_1/img_7.png)

pour l'instant nous somme dans le niveau 1, mais quelque sois le niveau toute ces étape serons a réalisé (mais les
événement pourrons être copier collé pour gagné du temps)

dans notre événement qu'on a créée pour le timer, nous allons rajouté une action qui est de renommé le texte par la valeur du "globalTime"

pour cela nous allons arrondire a 3 chiffre après la virgule afin de ne pas affiché une chiffre avec une 20en de décimal

![img_9.png](image_1/img_9.png)

une fois cela fait, nous allons mettre notre objet "Timer" en objet global afin de pouvoir faire les même action dans notre niveau 2

maintenent nous pouvons vérifier que tout fonctionne correctement en allans d'un niveau a l'autre


Maintenent nous allons Rajouté un affichage propre du timer dans la scene de victoire

![img_10.png](image_1/img_10.png)

![img_11.png](image_1/img_11.png)

puis dans les événement on vas rajouté qu'on met le texte a "Votre Chôno : " + globalTime
![img_12.png](image_1/img_12.png)





