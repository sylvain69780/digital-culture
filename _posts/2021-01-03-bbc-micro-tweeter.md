---
layout: default
title: Jouer avec BBC micro Bot !  La Fusee REPEAT ... UNTIL
tags: initiation
---
## Un autre type de boucle : REPEAT ... UNTIL

Faire un programme qui simule le lancement d'une fusée. Le programme s'arrête lorsque la fusée touche le sol.

* Données du problème
    * X va de 0 à 1279 , Y de 0 à 1023.
    * Postion de départ de la fusée en bas au centre de l'ecran
    * Vitesse initiale de la fusée VY=10 et VX=5
    * Decroissance de la vitesse horizontale VY à cause de la gravite A=-1

1. Ouvrir l'editeur [BBC Basic](https://bbcmic.ro/)
2. Choisir son mode Graphique dans [Page de Paul MALIN](https://translate.google.com/translate?sl=en&tl=fr&u=https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)
3. La position de départ de la fusée sera en bas a gauche de l'écran. (creer les variables ``` X=0``` ,``` Y=0``` )
4. La vitesse horizontale de la fusée sera de 5 et la vitesse verticale 10. Definir ``` VX=5```  et ``` VY=10``` 
5. La pesanteur va faire diminuer la vitesse horizontale de 0.1 à chaque fois, definir ``` A=0.1``` 
6. Positionez la fusee sur son lieu de lancement ```MOVE X,Y``` 
7. On calcule la nouvelle position de la fusee, la nouvelle vitesse horizontale.
8. La trajectoire de la fusée sera représentée par une ligne qu'on va tracer avec ```DRAW X,Y``` 
9. Boucler jusqu'à que que la fusée touche le sol ```REPEAT ... UNTIL Y<=0``` et afficher "TERMINE" à la fin.
10. Lancer des fusées aléatoirement
11. Donner une couleur aleatoire à chaque trajectoire.
12. Tweeter votre création.

**Marion**
```basic
MODE 2
FOR B=0 TO 3
X=0
Y=0
VX=5+RND(150)/10
VY=10+RND(150)/10
A=0.1
MOVE X,Y
REPEAT
GCOL 0,5+RND(15)
X=X+VX
Y=Y+VY
VY=VY-A
DRAW X,Y
UNTIL Y<=0
COLOUR 11
NEXT B
PRINT "END"
```
**Damien**
```basic
MODE2
FOR j=0 TO 3
GCOL 0,RND(15)
x=0 
y=0
vx=5
vy=5 + RND(10*10)/10
a=0.1
MOVE x,y
REPEAT
vy=vy-a
x=vx+x
y=vy+y
DRAW x,y
UNTIL y<=0
COLOUR 8
NEXT j
PRINT "terminus"
```


