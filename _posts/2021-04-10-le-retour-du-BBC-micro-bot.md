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

>En MODE 0 la résolution est 640x256 pixels mais 2 couleurs

[La page d'aide en Anglais](https://www.bbcmicrobot.com/learn/index.html) Utiliser la traduction dans Chrome **Traduire cette page**.

# Damien

![Image]({{ site.baseurl }}\assets\images\truchet_damien.png)

[Tweet](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE%202%5CnFOR%20c%3D0%20TO%2010%5CnGCOL%200%2CRND%28c%29%5CnFOR%20x%3D0TO7%5CnFOR%20y%3D0%20TO%209%5CnR%3DRND%281%29%5CnIF%20R%3C0.5%20THEN%20MOVE%20y*128%2Cx*128%20%3A%20MOVE%20y*128%2B127%2C%20x*128%20%3A%20PLOT%2085%2Cy*128%2B127%2Cx*128%2B127%5CnIF%20R%3E0.5%20THEN%20MOVE%20y*128%2Cx*128%2B127%20%3A%20MOVE%20y*128%2B127%2C%20x*128%20%3A%20PLOT%2085%2Cy*128%2B127%2Cx*128%2B127%5CnNEXT%20y%5CnNEXT%20x%5CnNEXT%20c%22%7D)

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

![Image]({{ site.baseurl }}\assets\images\truchet_marion.png)

[Tweet](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE%200%5CnCOLOUR%201%5CnFOR%20Longueur%3D0%20TO%209%5CnFOR%20Hauteur%3D0%20TO%209%5CnR%3DRND%281%29%20%5CnIF%20R%3E0.5%20THEN%20MOVE%20Longueur*128%2CHauteur*128%20%3A%20MOVE%20Longueur*128%2B127%2CHauteur*128%20%3A%20PLOT%2085%2CLongueur*128%2B127%2CHauteur*128%2B127%5CnIF%20R%3C0.5%20THEN%20MOVE%20Longueur*128%2CHauteur*128%2B127%20%3A%20MOVE%20Longueur*128%2B127%2CHauteur*128%2B127%20%3A%20PLOT%2085%2CLongueur*128%2B127%2CHauteur*128%5CnNEXT%20Hauteur%5CnNEXT%20Longueur%22%7D)

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

# Papa essaie de faire mieux ...

```basic
MODE 2
A%=0
B%=1
C%=3
D%=2
FOR C=1 TO 6
GCOL 0,C
FOR Y=0 TO 7
FOR X=0 TO 9
R% = INT(RND(1)*4)
IF R%=0 PROCTRI(X,Y,A%,B%,C%)
IF R%=1 PROCTRI(X,Y,B%,C%,D%)
IF R%=2 PROCTRI(X,Y,C%,D%,A%)
IF R%=3 PROCTRI(X,Y,D%,A%,B%)
NEXT X
NEXT Y
NEXT C
END
DEF PROCTRI(X,Y,AA%,BB%,CC%)
SCALE=128
MOVE (X+(AA% MOD 2))*SCALE,(Y+(AA% DIV 2))*SCALE
MOVE (X+(BB% MOD 2))*SCALE,(Y+(BB% DIV 2))*SCALE
PLOT 85,(X+(CC% MOD 2))*SCALE,(Y+(CC% DIV 2))*SCALE
ENDPROC
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
