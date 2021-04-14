---
layout: default
title: BBC micro bot, hexagones
tags: initiation
---
# Introduction

[Sophie Wilson](https://fr.wikipedia.org/wiki/Sophie_Wilson) est la créatrice du BBC micro et du BBC basic, commercialisé en **1981**.

[Dominic Pajak](https://www.bbcmicrobot.com/learn/index.html) amateur de vieux micros a été très surpris du succès de son BBC Micro bot tweeter. 

Qui aurait pensé qu'autant de gens comme Paul Malin allaient s'amuser avec cette antiquité de 1981 ?

# Problème

On veut realiser un pavage [hexagonal](https://fr.wikipedia.org/wiki/Hexagone) à l'écran.
![hexagone](https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/Regular_polygon_6_annotated.svg/langfr-280px-Regular_polygon_6_annotated.svg.png)

Pourquoi ? Par ce que la France est aussi parfois surnomé l'hexagone, mais aussi par ce que les hexagones, c'est **cool** comme on va le voir.

Comment faire pour determiner les coordonnées X,Y de chaque sommet de l'hexagone pour pouvoir tracer des lignes autour ?

# Tracer un hexagone à l'écran

Sur une feuille de papier, dessiner un hexagone de coté 2 cm, **pointe en haut** comme sur la page wikipedia, trouver un triangle rectange et appliquer pythagore pour trouver les coordonnées X et Y du point à droit de l'hegagone.

- [BBC Basic Editor](https://bbcmic.ro/)
- [La page d'aide en Anglais de Dominic Pajak le createur du BBC micro bot](https://www.bbcmicrobot.com/learn/index.html)
- [La page de Paul Malin sur les fonctions graphiques](https://blog.mousefingers.com/post/bbc/bbc_reference/)

Pour centrer l'origine 0,0 au centre de l'écran (plus partique)
```basic
VDU29,640;256;
```

- On ne va utiliser que les commandes MOVE puis DRAW et 2 variables A et B, plus le Zero pour tracer l'hexagone.













# Contour de l'Hexagone 
```basic
MODE0
VDU29,640;512;
S=128
A=S*SQR(3)
B=S
MOVE A,-B
DRAW A,B
DRAW 0,A
DRAW -A,B
DRAW -A,B
DRAW -A,-B
DRAW 0,-A
DRAW A,-B
```

# Deplacer le trace de l'exagone dans une procedure
```basic
MODE0
VDU29,640;512;
S=128
A=S*SQR(3)
B=S
PROCHEXA
END
DEF PROCHEXA
MOVE A,-B
DRAW A,B
DRAW 0,A
DRAW -A,B
DRAW -A,B
DRAW -A,-B
DRAW 0,-A
DRAW A,-B
ENDPROC
```
# Colorier l'hexagone

```basic
MODE2
VDU29,640;512;
S=128
A=S*SQR(3)
A=2*S
B=S
PROCHEXA
END
DEF PROCHEXA
PROCTRI(A,-B,A,B,2)
PROCTRI(A,B,0,A,3)
PROCTRI(0,A,-A,B,4)
PROCTRI(-A,B,-A,-B,5)
PROCTRI(-A,-B,0,-A,6)
PROCTRI(0,-A,A,-B,7)
ENDPROC
DEF PROCTRI(X1,Y1,X2,Y2,C)
GCOL 0,C
MOVE 0,0 : MOVE X1,Y1 : PLOT 85,X2,Y2
ENDPROC
```

# Colorier l'hexagone avec des bords noirs

MODE2
VDU29,640;512;
S=64
A=S*SQR(3)
A=2*S
B=S
PROCHEXA
END
DEF PROCHEXA
PROCTRI(A,-B,A,B,2)
PROCTRI(A,B,0,A,3)
PROCTRI(0,A,-A,B,4)
PROCTRI(-A,B,-A,-B,5)
PROCTRI(-A,-B,0,-A,6)
PROCTRI(0,-A,A,-B,7)
ENDPROC
DEF PROCTRI(X1,Y1,X2,Y2,C)
GCOL 0,C
MOVE 0,0 : MOVE X1,Y1 : PLOT 85,X2,Y2
GCOL 0,0
MOVE 0,0 : DRAW X1,Y1 : DRAW X2,Y2 : DRAW 0,0
ENDPROC

```basic

    MODE2
    VDU29,640;512;
    S=64
    A=S*SQR(3)
    A=2*S
    B=S
    PROCHEXA
    VDU29,640+A*2;512;
    PROCHEXA
    END
    DEF PROCHEXA
    PROCTRI(A,-B,A,B,6)
    PROCTRI(A,B,0,A,7)
    PROCTRI(0,A,-A,B,7)
    PROCTRI(-A,B,-A,-B,4)
    PROCTRI(-A,-B,0,-A,4)
    PROCTRI(0,-A,A,-B,6)
    ENDPROC
    DEF PROCTRI(X1,Y1,X2,Y2,C)
    GCOL 0,C
    MOVE 0,0 : MOVE X1,Y1 : PLOT 85,X2,Y2
    ENDPROC
    DEF PROCTRI2(X1,Y1,X2,Y2,C)
    GCOL 0,6
    MOVE 0,0 : DRAW X1,Y1 : DRAW X2,Y2 : DRAW 0,0
    ENDPROC
```


# Notes

- [2 Hexagones effet cube 3D bleu](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnVDU29%2C640%3B512%3B%5CnS%3D64%5CnA%3DS*SQR%283%29%5CnA%3D2*S%5CnB%3DS%5CnPROCHEXA%5CnVDU29%2C640%2BA*2%3B512%3B%5CnPROCHEXA%5CnEND%5CnDEF%20PROCHEXA%5CnPROCTRI%28A%2C-B%2CA%2CB%2C6%29%5CnPROCTRI%28A%2CB%2C0%2CA%2C7%29%5CnPROCTRI%280%2CA%2C-A%2CB%2C7%29%5CnPROCTRI%28-A%2CB%2C-A%2C-B%2C4%29%5CnPROCTRI%28-A%2C-B%2C0%2C-A%2C4%29%5CnPROCTRI%280%2C-A%2CA%2C-B%2C6%29%5CnENDPROC%5CnDEF%20PROCTRI%28X1%2CY1%2CX2%2CY2%2CC%29%5CnGCOL%200%2CC%5CnMOVE%200%2C0%20%3A%20MOVE%20X1%2CY1%20%3A%20PLOT%2085%2CX2%2CY2%5CnENDPROC%5CnDEF%20PROCTRI2%28X1%2CY1%2CX2%2CY2%2CC%29%5CnGCOL%200%2C6%5CnMOVE%200%2C0%20%3A%20DRAW%20X1%2CY1%20%3A%20DRAW%20X2%2CY2%20%3A%20DRAW%200%2C0%5CnENDPROC%5Cn%22%7D)

