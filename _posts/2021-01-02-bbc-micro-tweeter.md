---
layout: default
title: Jouer avec BBC micro Bot ! Faire une boucle
tags: initiation
---
## Programmer en basic, Un programme plus compliqué

Nous allons continuer à nous familiariser avec le BBC Basic de 1980
Objectifs : 
### 1 Faire une boucle.
```basic
FOR I=0 TO 10
PRINT I
NEXT I
```
### 2 Faire un Contours du cercle

Trouver dans la page de Paul Malin

[fun with BBC micro](https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)

Comment change-t-on le diamètre du cercle ?

### 3 Faire un cercle de plus en plus grand

### Rappel des outils
coordonnées X et Y
X va de 0 à 1279 , Y de 0 à 1023.
Donc 640,512 c'est toujours le centre

[Lien vers l'éditeur en ligne](https://bbcmic.ro/)
Control+ENTREE execute le programme !

[Simulateur d'Ordinateur BBC Micro](https://bbc.godbolt.org/)

[Page de Paul MALIN](https://translate.google.com/translate?sl=en&tl=fr&u=https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)

S'inspirer des exemple Owlet Editor 
Drawing shapes
Pour faire un dessin pour le robot Tweeter.

Les couleurs physiques suivantes sont disponibles:

Valeur de couleur physique	Couleur
0	noir
1	rouge
2	vert
3	Jaune
4	bleu
5	magenta
6	cyan
sept	blanc
8	clignotant noir-blanc
9	clignotant rouge-cyan
dix	vert-magenta clignotant
11	clignotant jaune-bleu
12	clignotant bleu-jaune
13	vert magenta clignotant
14	clignotant cyan-rouge
15	clignotant blanc-noir



Ci-dessous Le programme réalisé au dernier cours.

```basic
MODE 2
MOVE 0,600
GCOL 0,14
DRAW 650,1000
DRAW 1279,600
DRAW 0,600
GCOL 0,4
MOVE 100,20
DRAW 1000,20
DRAW 1000,590
DRAW 100,590
DRAW 100,20
```

