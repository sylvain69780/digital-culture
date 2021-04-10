---
layout: default
title: Le retour du BBC micro bot, pavages
tags: initiation
---
# Question

Comment utiliser l'ordinateur pour crée du contenu (musique, images) qu'on puisse utiliser librement ?

# Objectifs

- TAPER du code sur [BBC BASIC EDITOR](https://bbcmic.ro/), exercice au clavier
    - CTRL+ENTER pour compiler
- Choisir son mode graphique
- Réaliser 2 boucles FOR imriquées pour réaliser un pavage à l'écran
- Essayer de réaliser un [pavage de Truchet](http://images.math.cnrs.fr/Les-pavages-de-Truchet.html)

Mode 0 640 256

# Damien

![Tweet](https://twitter.com/i/status/1380939769073565696)

```basic
MODE 2
FOR c=0 TO 10
GCOL 0,RND(c)
FOR x=0TO7
FOR y=0 TO 9
R=RND(1)
IF R<0.5 THEN MOVE y*128,x*128 : MOVE y*128+127, x*128 : PLOT 85,y*128+127,x*128+127
IF R>0.5 THEN MOVE y*128,x*128+127 : MOVE y*128+127, x*128 : PLOT 85,y*128+127,x*128+127
NEXT y
NEXT x
NEXT c
```

# Marion

![Tweet](https://twitter.com/i/status/1380940331840122888)

```basic
MODE 0
COLOUR 1
FOR Longueur=0 TO 9
FOR Hauteur=0 TO 9
R=RND(1) 
IF R>0.5 THEN MOVE Longueur*128,Hauteur*128 : MOVE Longueur*128+127,Hauteur*128 : PLOT 85,Longueur*128+127,Hauteur*128+127
IF R<0.5 THEN MOVE Longueur*128,Hauteur*128+127 : MOVE Longueur*128+127,Hauteur*128+127 : PLOT 85,Longueur*128+127,Hauteur*128
NEXT Hauteur
NEXT Longueur
```

# Exemple

S'inspirer du programme exemple ci-dessous, mais pas de copier coller !

Utiliser les cours précédents pour retrouver les fonctions de dessin du Basic BBC Micro

```basic
MODE2
FOR N=1 TO 11
x=N*100
y=100
vx=0
vy=100+RND(700)/10
a=20
diff=RND(15)
FOR image=1 TO 15
GCOL 0,image+diff MOD 15
MOVE x,y
PLOT 153,40,0
x=vx+x
y=vy+y
NEXT image
NEXT N
K=1 : REM logical colour to keep 
REPEAT
FOR L=0 TO 15 : REM for each logical colour
P=0 : REM physical colour to set  
IF L=K THEN P=1 : REM set physical colour to magenta
VDU 19,L,P,0,0,0
NEXT L
K=K+1
IF K>15 THEN K=1
attend=INKEY(10)
UNTIL FALSE
```
