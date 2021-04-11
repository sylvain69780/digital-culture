---
layout: default
title: Jouer avec BBC micro Bot ! Faire un pavage de ronds a l'ecran.
tags: initiation
---
### Faire une programme qui affiche des ronds pleins colorés dans une grille de 4 de large par 3 de hauteur.

* Données du problèmes
    * Rayon des cercles : 40
    * Premier cercle à 200,200
    * Espacement entre les cercles : 300
    * 4 cercles en largeur et 3 en hauteur
1. Ouvrir l'editeur [BBC Basic](https://bbcmic.ro/)
2. Choisir son mode Graphique dans [Page de Paul MALIN](https://translate.google.com/translate?sl=en&tl=fr&u=https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)
3. Positioner le début du dessin (centre du cercle) avec ```MOVE X,Y``` 
4. Tracer un cercle plein avec ```PLOT 153,rayon,0```
5. Changer la couleur du cercle avec ```GCOL 0```
6. Faire une ligne de cercle avec une boucle avec ```FOR I=0 TO ...```
7. Faire la seconde ligne de cercles
8. Donner des couleurs aléatoires avec la fonction ```RAND(...)```
9. Décaler chaque rond d'une valeur aleatoire avec la fonction RAND(nombre)
10. Donner à chaque cercle un diamètre différent
11. Poster chacun votre creation sur Tweeter et sur le blog de Paul Malin pour lui faire plaisir.

Réponse
```basic
10 MODE 2
20 FOR J=0 TO 2
30 FOR I=0 TO 3
40 GCOL 0,RND(10)
50 MOVE I*300+200+RND(100),J*300+200+RND(100)
60 PLOT 153,40+RND(100),0
70 NEXT I
80 NEXT J
```
