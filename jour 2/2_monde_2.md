# Le second monde

## Ajout des tilemaps

Maintenant que nous avons créé la scène du second monde, nous allons pouvoir y ajouter une nouvelle tilemap.
Afin de varier les décors, nous allons utiliser une nouvelle tilemap que nous allons créer.

Nous allons cliquer sur le petit "plus" pour créer un nouvel objet TileMap que nous allons nommer "bateau" avec une taille de

32.

![img.png](image_2/img.png)
![img_1.png](image_2/img_1.png)

Nous allons choisir le fichier "ship_tileset.png" qui se trouve dans le dossier "tileset" que vous avez téléchargé.

![img_2.png](image_2/img_2.png)
![img_3.png](image_2/img_3.png)

Une fois cela fait, nous allons mettre les collisions sur les textures que nous voulons.

![img_18.png](image_2/img_18.png)
Nous ne sélectionnons pas les éléments inférieurs, comme sur l'image, car cela nous servira de fond.

Ensuite, nous allons ajouter le comportement "Plateforme" à notre tilemap.

![img_5.png](image_2/img_5.png)
![img_6.png](image_2/img_6.png)

Une fois cela fait, nous pouvons appliquer les modifications.

Comme pour les autres objets, nous allons passer celui-ci dans les objets globaux afin de pouvoir l'utiliser dans toutes
les scènes.

Maintenant, nous allons ajouter un tileset "plateforme" qui permettra d'ajouter des plateformes sur lesquelles nous
pourrons passer à travers.

Pour cela, nous allons créer à nouveau une TileMap que nous appellerons "plateforme" avec une taille de 32.

![img_7.png](image_2/img_7.png)
Nous allons choisir le fichier "platform_tileset.png" qui se trouve dans le dossier "tileset" que vous avez téléchargé.

![img_8.png](image_2/img_8.png)

Une fois cela fait, nous allons mettre les collisions sur les textures que nous voulons.

![img_9.png](image_2/img_9.png)

Ensuite, nous allons ajouter le comportement "Plateforme" à notre tilemap.
Dans le type, nous allons mettre "Jumpthru" afin de pouvoir passer à travers les plateformes.

![img_10.png](image_2/img_10.png)

Puis nous allons appliquer les modifications et mettre notre objet en objet global.

## Organisation

Nous commençons à avoir beaucoup d'objets globaux, il est donc important de bien les organiser afin de ne pas se perdre.

Pour cela, nous allons créer des dossiers.
Pour faire cela, nous allons faire un clic droit sur "Objets globaux", puis cliquer sur "Ajouter un dossier".

![img_11.png](image_2/img_11.png)

Nous allons créer un dossier "TileMap" dans lequel nous allons mettre les deux TileMap que nous avons créées.

![img_12.png](image_2/img_12.png)

Pour déplacer facilement les objets, nous avons juste à les glisser dans le dossier voulu.

Nous allons également faire cela pour les "items", l'"HUD" et les "entités" afin de bien organiser notre projet.

![img_13.png](image_2/img_13.png)

## Créer le monde

Nous allons maintenant pouvoir commencer la création du monde. Pour cela, nous allons glisser notre TileMap "bateau" et
notre TileMap "plateforme" dans la scène.

![img_14.png](image_2/img_14.png)

Afin que tout fonctionne correctement, nous allons cliquer sur l'objet "bateau", puis, dans l'onglet "Propriété", nous
allons mettre les coordonnées à 0 0.
![img_15.png](image_2/img_15.png)

Nous allons faire la même manipulation avec l'objet "plateforme" et mettre ses coordonnées à 0 32.

![img_16.png](image_2/img_16.png)

Cela doit donner ceci en jeu.

![img_17.png](image_2/img_17.png)

À partir de là, nous avons juste à créer notre niveau.
Nous laisserons quelques trous dans le mur de fond afin de pouvoir mettre des fenêtres ensuite.

![img_19.png](image_2/img_19.png)

Pour sélectionner une autre tilemap présente dans la scène, il suffit de cliquer dessus dans la liste des instances :
![img_20.png](image_2/img_20.png)

Faites bien attention à ce que la tilemap des plateformes ait une valeur Z plus élevée que la tilemap du bateau.

![img_21.png](image_2/img_21.png)

Si ce n'est pas le cas, il suffit de cliquer sur l'instance de la plateforme et de changer son Z pour qu'il soit plus
élevé.

![img_22.png](image_2/img_22.png)
![img_23.png](image_2/img_23.png)

Avant de continuer en mettant en place les décorations et le reste, nous allons mettre le joueur dans la scène afin de voir
si tout fonctionne correctement.

Pour descendre des plateformes, il suffit d'appuyer sur la touche "S".

Nous pouvons également voir que la caméra est de nouveau éloignée. Nous allons régler cela tout de suite en allant dans les
événements de la scène "Niveau_2", puis en ajoutant un événement vide.

![img_24.png](image_2/img_24.png)
Nous allons ajouter les mêmes actions que celles que nous avions mises dans la première scène.

![img_25.png](image_2/img_25.png)

Nous réglerons le reste des problèmes d'animation et les autres éléments plus tard.

## Décoration

Maintenant, nous allons ajouter les décorations.

La manipulation sera la même pour chaque décoration que nous allons ajouter. La seule différence sera les textures utilisées.

Nous allons créer un nouveau dossier "décoration" dans les objets globaux. Nous y mettrons nos décorations.

![img_26.png](image_2/img_26.png)

Nous allons créer un nouveau sprite.

![img_27.png](image_2/img_27.png)
![img_28.png](image_2/img_28.png)
![img_29.png](image_2/img_29.png)

Puis nous allons valider et mettre le sprite dans le dossier nouvellement créé.

Nous allons faire pareil pour les lumières de fenêtre, les tonneaux, les bougies, les chaînes et les portes. La différence est que, pour
les portes, nous allons mettre les deux animations directement dans le même sprite.

À la fin, nous devons avoir ceci :
![img_30.png](image_2/img_30.png)
![img_31.png](image_2/img_31.png)
![img_32.png](image_2/img_32.png)
![img_33.png](image_2/img_33.png)

Pour les tonneaux et les bouteilles, il faut un sprite par image.
![img_34.png](image_2/img_34.png)
![img_35.png](image_2/img_35.png)
![img_36.png](image_2/img_36.png)

Maintenant, nous pouvons placer les décorations dans le monde.

![img_37.png](image_2/img_37.png)

Enfin, dernière étape, il faut que nous mettions les pièces, les potions et le diamant de fin. Nous ajouterons les ennemis plus tard,
quand nous en créerons de nouveaux.

![img_38.png](image_2/img_38.png)

Il ne faut pas oublier ensuite de mettre la valeur Z du joueur au-dessus de la plus grande valeur Z, que nous pouvons trouver dans la liste des instances.

![img_39.png](image_2/img_39.png)
![img_40.png](image_2/img_40.png)
