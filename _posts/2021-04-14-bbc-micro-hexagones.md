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

Pourquoi ? Par ce que la France est aussi parfois surnomée l'hexagone, mais aussi par ce que les hexagones, c'est **cool** comme on va le voir.

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

# Etapes si vous etes perdus

[Contour de l'Hexagone](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE0%5CnVDU29%2C640%3B512%3B%5CnS%3D128%5CnA%3DS*SQR%283%29%5CnB%3DS%5CnMOVE%20A%2C-B%5CnDRAW%20A%2CB%5CnDRAW%200%2CA%5CnDRAW%20-A%2CB%5CnDRAW%20-A%2CB%5CnDRAW%20-A%2C-B%5CnDRAW%200%2C-A%5CnDRAW%20A%2C-B%5Cn%22%7D) 

[Deplacer le trace de l'exagone dans une procedure](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE0%5CnVDU29%2C640%3B512%3B%5CnS%3D128%5CnA%3DS*SQR%283%29%5CnB%3DS%5CnPROCHEXA%5CnEND%5CnDEF%20PROCHEXA%5CnMOVE%20A%2C-B%5CnDRAW%20A%2CB%5CnDRAW%200%2CA%5CnDRAW%20-A%2CB%5CnDRAW%20-A%2CB%5CnDRAW%20-A%2C-B%5CnDRAW%200%2C-A%5CnDRAW%20A%2C-B%5CnENDPROC%5Cn%22%7D)

[Colorier l'hexagone](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnVDU29%2C640%3B512%3B%5CnS%3D128%5CnA%3DS*SQR%283%29%5CnA%3D2*S%5CnB%3DS%5CnPROCHEXA%5CnEND%5CnDEF%20PROCHEXA%5CnPROCTRI%28A%2C-B%2CA%2CB%2C2%29%5CnPROCTRI%28A%2CB%2C0%2CA%2C3%29%5CnPROCTRI%280%2CA%2C-A%2CB%2C4%29%5CnPROCTRI%28-A%2CB%2C-A%2C-B%2C5%29%5CnPROCTRI%28-A%2C-B%2C0%2C-A%2C6%29%5CnPROCTRI%280%2C-A%2CA%2C-B%2C7%29%5CnENDPROC%5CnDEF%20PROCTRI%28X1%2CY1%2CX2%2CY2%2CC%29%5CnGCOL%200%2CC%5CnMOVE%200%2C0%20%3A%20MOVE%20X1%2CY1%20%3A%20PLOT%2085%2CX2%2CY2%5CnENDPROC%5Cn%22%7D)

[Colorier l'hexagone avec des bords noirs](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnVDU29%2C640%3B512%3B%5CnS%3D64%5CnA%3DS*SQR%283%29%5CnA%3D2*S%5CnB%3DS%5CnPROCHEXA%5CnEND%5CnDEF%20PROCHEXA%5CnPROCTRI%28A%2C-B%2CA%2CB%2C2%29%5CnPROCTRI%28A%2CB%2C0%2CA%2C3%29%5CnPROCTRI%280%2CA%2C-A%2CB%2C4%29%5CnPROCTRI%28-A%2CB%2C-A%2C-B%2C5%29%5CnPROCTRI%28-A%2C-B%2C0%2C-A%2C6%29%5CnPROCTRI%280%2C-A%2CA%2C-B%2C7%29%5CnENDPROC%5CnDEF%20PROCTRI%28X1%2CY1%2CX2%2CY2%2CC%29%5CnGCOL%200%2CC%5CnMOVE%200%2C0%20%3A%20MOVE%20X1%2CY1%20%3A%20PLOT%2085%2CX2%2CY2%5CnGCOL%200%2C0%5CnMOVE%200%2C0%20%3A%20DRAW%20X1%2CY1%20%3A%20DRAW%20X2%2CY2%20%3A%20DRAW%200%2C0%5CnENDPROC%5Cn%22%7D)

# Notes

- [2 Hexagones effet cube 3D bleu](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnVDU29%2C640%3B512%3B%5CnS%3D64%5CnA%3DS*SQR%283%29%5CnA%3D2*S%5CnB%3DS%5CnPROCHEXA%5CnVDU29%2C640%2BA*2%3B512%3B%5CnPROCHEXA%5CnEND%5CnDEF%20PROCHEXA%5CnPROCTRI%28A%2C-B%2CA%2CB%2C6%29%5CnPROCTRI%28A%2CB%2C0%2CA%2C7%29%5CnPROCTRI%280%2CA%2C-A%2CB%2C7%29%5CnPROCTRI%28-A%2CB%2C-A%2C-B%2C4%29%5CnPROCTRI%28-A%2C-B%2C0%2C-A%2C4%29%5CnPROCTRI%280%2C-A%2CA%2C-B%2C6%29%5CnENDPROC%5CnDEF%20PROCTRI%28X1%2CY1%2CX2%2CY2%2CC%29%5CnGCOL%200%2CC%5CnMOVE%200%2C0%20%3A%20MOVE%20X1%2CY1%20%3A%20PLOT%2085%2CX2%2CY2%5CnENDPROC%5CnDEF%20PROCTRI2%28X1%2CY1%2CX2%2CY2%2CC%29%5CnGCOL%200%2C6%5CnMOVE%200%2C0%20%3A%20DRAW%20X1%2CY1%20%3A%20DRAW%20X2%2CY2%20%3A%20DRAW%200%2C0%5CnENDPROC%5Cn%22%7D)

- [Hexagones effet 3D](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE1%5CnC1%3D2%5CnC2%3D1%5CnC3%3D0%5CnVDU29%2C640%3B512%3B%5CnS%3D16%5CnA%3DS*SQR%283%29%5CnA%3D2*S%5CnB%3DS%5CnFOR%20J%3D0%20TO%2011*2%5CnFOR%20I%3D0%20TO%2010*2%5CnR%3DINT%28RND%281%29*2%29%5CnR%3DINT%281%2BCOS%280.6*%28I%2BJ%29%29%29%5CnVDU29%2CI*A*2%2B%28J%20MOD%202%29*S*2%3BJ*S*3%3B%5CnIF%20R%3D0%20THEN%20PROCHEXA%5CnIF%20R%3D1%20THEN%20PROCHEXA2%5CnNEXT%20I%5CnNEXT%20J%5CnEND%5CnDEF%20PROCHEXA%5CnPROCTRI%28A%2C-B%2CA%2CB%2CC3%29%5CnPROCTRI%28A%2CB%2C0%2CA%2CC1%29%5CnPROCTRI%280%2CA%2C-A%2CB%2CC1%29%5CnPROCTRI%28-A%2CB%2C-A%2C-B%2CC2%29%5CnPROCTRI%28-A%2C-B%2C0%2C-A%2CC2%29%5CnPROCTRI%280%2C-A%2CA%2C-B%2CC3%29%5CnGCOL%200%2CC1%5CnMOVE%20A%2CB%5CnDRAW%200%2CA%5CnDRAW%20-A%2CB%5CnDRAW%200%2C0%5CnDRAW%20A%2CB%5CnMOVE%200%2C0%5CnDRAW%20-A%2CB%5CnDRAW%20-A%2C-B%5CnDRAW%200%2C-A%5CnDRAW%200%2C0%5CnMOVE%200%2C0%5CnDRAW%200%2C-A%5CnDRAW%20A%2C-B%5CnDRAW%20A%2CB%5CnDRAW%200%2C0%5Cn%5CnENDPROC%5CnDEF%20PROCHEXA2%5CnPROCTRI%28A%2C-B%2CA%2CB%2CC2%29%5CnPROCTRI%28A%2CB%2C0%2CA%2CC2%29%5CnPROCTRI%280%2CA%2C-A%2CB%2CC3%29%5CnPROCTRI%28-A%2CB%2C-A%2C-B%2CC3%29%5CnPROCTRI%28-A%2C-B%2C0%2C-A%2CC1%29%5CnPROCTRI%280%2C-A%2CA%2C-B%2CC1%29%5CnGCOL%200%2CC1%5CnMOVE%200%2C0%5CnDRAW%20-A%2C-B%5CnDRAW%200%2C-A%5CnDRAW%20A%2C-B%5CnDRAW%200%2C0%5CnMOVE%200%2C0%5CnDRAW%20A%2C-B%5CnDRAW%20A%2CB%5CnDRAW%200%2CA%5CnDRAW%200%2C0%5CnMOVE%200%2C0%5CnDRAW%200%2CA%5CnDRAW%20-A%2CB%5CnDRAW%20-A%2C-B%5CnDRAW%200%2C0%5Cn%5CnENDPROC%5CnDEF%20PROCTRI%28X1%2CY1%2CX2%2CY2%2CC%29%5CnGCOL%200%2CC%5CnMOVE%200%2C0%20%3A%20MOVE%20X1%2CY1%20%3A%20PLOT%2085%2CX2%2CY2%5CnENDPROC%5Cn%22%7D)
