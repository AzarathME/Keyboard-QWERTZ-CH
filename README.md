Cette librairie est créée spécialement pour les utilisateurs d'Arduino ayant des claviers en QWERTZ (Suisse).

# Installation :

Pour modifier la disposition de votre clavier, il suffit de copier et de coller les fichiers ("Keyboard.h" et "Keyboard.cpp") dans le dossier source (src) de la lib "Keyboard" :

> "C:\Program Files (x86)\Arduino\libraries\Keyboard\src"

Il n'y a pas besoin de redémarrage du logiciel Arduino (Vous pouvez toujours le faire, on ne sait jamais !).

Pour utiliser des caractères spéciaux, tel : | [] {} # , il suffit de suivre l'exemple :

```C
Keyboard.press(KEY_LEFT_CTRL);
Keyboard.press(KEY_LEFT_ALT);
Keyboard.print("|[]{}#");
Keyboard.releaseAll();
```
Et, en sortie, on a :

> |[]{}#

# Comment ça marche !

Il se peut qu'il y'a des disfonctionnement avec certaines touches. 
Dans ce cas-ci, il faudrait mettre la main à la pâte et bidouiller les codes.

![alt text](https://scriptel.com/KeyboardEmulationAPI/JavaScript/images/keyboard-identifiers.png)

> Voici donc les valeurs décimaux de chaque touche du clavier.

Pour commencer, il suffit de convertir la valeur décimal de la touche de votre choix en hexadécimal.
Par exemple, la touche "AD01" qui est pour moi la touche "Q" a comme valeur : 20 

> On le convertit sur un site comme : https://www.rapidtables.com/convert/number/decimal-to-hex.html

Ce qui nous donne une valeur de "0x14" en hexadécimal. (Le "0x" est un préfixe pour dire que c'est de l'hexa :) )
Il faut se rendre ensuite dans `Keyboard.cpp` et modifier l'ancien hexa par le nouveau.

![alt text](https://image.noelshack.com/fichiers/2019/23/6/1560031146-1.png)
> Pour ma part, c'est déjà fait.

Vous avez une idée du concept. Maintenant à vous de jouer !
