---
layout: default
title: BBC micro bot, truchet en boucle
tags: initiation
---
# Intro

Avant d'aller plus loin, on va revoir ce qu'on a fait la dernière fois

On va faire un nouveau pavage carré, mais varié

[Sebastien Truchet](https://fr.wikipedia.org/wiki/S%C3%A9bastien_Truchet) inventeur de ces pavages, est né à Lyon en 1657 ! Il ne pensait pas qu'on allait encore parler de lui 360 ans plus tard. Bravo Sébastien !

A vous de jouer maintenant, je compte sur vous pour que je puisse décorer mon blog de vos meilleures creations.

# Les liens utiles

Utiliser la traduction automatique en Francais disponible dans Chrome

>En echauffement, commencer par afficher les puissances de 2 : 1,2,4,8,16,32,64 .. 4096
>Utiliser des puissances de 2 pour des longeurs est tres utile 
>C'est un moyen d'eviter d'avoir des pixels de travers lorsqu'on trace des lignes.

- [BBC Basic Editor](https://bbcmic.ro/)
- [La page d'aide en Anglais de Dominic Pajak le createur du BBC micro bot](https://www.bbcmicrobot.com/learn/index.html)
- [Page de Paul MALIN d'intro au BBC micro bot](https://translate.google.com/translate?sl=en&tl=fr&u=https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)
- [La page de Paul Malin sur les fonctions graphiques](https://blog.mousefingers.com/post/bbc/bbc_reference/)
- [ROM d'extension](file:///C:/Users/sylvain.lecourtois/Downloads/Graphics_Extension_ROM%20(1).pdf)

# Etapes

Utiliser les exemples ci-dessous, mais pas de couper coller

- [Dessiner un CARRE de coté S=256 centré à l'écran](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D128%5CnVDU%2029%2C640%3B512%3B%5CnMOVE%200%2C0%5CnPLOT%20153%2C100%2C0%5Cn%22%7D)

La commande ci-dessous permet de redefinir l'origine 0,0 du repere de l'ecran, ce qui est bien pratique.

```basic
VDU 29,640;512;
```
[solution](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D256%5CnVDU%2029%2C640%3B512%3B%5CnMOVE%200%2C0%5CnT%3DS%2F2%5CnMOVE%20T%2CT%5CnDRAW%20-T%2CT%20%5CnDRAW%20-T%2C-T%20%5CnDRAW%20T%2C-T%20%5CnDRAW%20T%2CT%20%5Cn%5Cn%22%7D)

- On va tracer des arcs de cercle qui vont relier les cotés adjacents du carré

[Tracé dans Desmos](https://www.desmos.com/calculator/of9rjtqrlo)

Pour tracer un cercle : centre, point de depart, point d'arrivée.
```basic
REM Trace un arc de cercle
MOVE T,T : MOVE 0,T : PLOT &A5,T,0
REM Trace un secteur plein
MOVE T,T : MOVE 0,T : PLOT &B5,T,0
```

[Etape 1](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE1%5CnS%3D128*4%5CnVDU%2029%2C640%3B512%3B%5CnMOVE%200%2C0%5CnT%3DS%2F2%5CnMOVE%20T%2CT%5CnDRAW%20-T%2CT%20%5CnDRAW%20-T%2C-T%20%5CnDRAW%20T%2C-T%20%5CnDRAW%20T%2CT%20%5CnGCOL%200%2C1%20%3A%20PROCS%2811%2F8%2C%26B5%29%5CnGCOL%200%2C2%20%3A%20PROCS%2810%2F8%2C%26B5%29%5CnGCOL%200%2C3%20%3A%20PROCS%281%2C%26A5%29%5CnGCOL%200%2C1%20%3A%20PROCS%286%2F8%2C%26B5%29%5CnGCOL%200%2C0%20%3A%20PROCS%285%2F8%2C%26B5%29%5CnEND%5CnDEF%20PROCS%28R%2CCODE%29%5CnMOVE%20T%2CT%20%3A%20MOVE%20T-T*R%2CT%20%3A%20PLOT%20CODE%2CT%2CT-T*R%5CnENDPROC%22%7D)

[Terminé en couleurs](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D128*3%5CnT%3DS%2F2%5CnFOR%20I%3D0%20TO%205%5CnFOR%20J%3D0%20TO%205%5CnVDU%2029%2CI*S%3BJ*S%3B%5CnREM%20VDU%2029%2C640%3B512%3B%5CnA%3DRND%282%29%5CnIF%20A%3D1%20THEN%20FX%3D1%20%3A%20FY%3D1%20%3A%20PROCR%20%3A%20FX%3D-1%20%3A%20FY%3D-1%20%3A%20PROCR%5CnIF%20A%3D2%20THEN%20FX%3D-1%20%3A%20FY%3D1%20%3A%20PROCR%20%3A%20FX%3D1%20%3A%20FY%3D-1%20%3A%20PROCR%5CnNEXT%20J%5CnNEXT%20I%5CnEND%5CnDEF%20PROCR%5CnGCOL%200%2C1%20%3A%20PROCS%2811%2F8%2C%26B5%29%20%5CnGCOL%200%2C2%20%3A%20PROCS%2810%2F8%2C%26B5%29%5CnGCOL%200%2C0%20%3A%20PROCS%281%2C%26A5%29%5CnGCOL%200%2C1%20%3A%20PROCS%286%2F8%2C%26B5%29%5CnGCOL%200%2C0%20%3A%20PROCS%285%2F8%2C%26B5%29%5CnENDPROC%5CnDEF%20PROCS%28R%2CCODE%29%5CnIF%20FX*FY%3D%201%20THEN%20MOVE%20T*FX%2CT*FY%20%3A%20MOVE%20%28T-T*R%29*FX%2CT*FY%20%3A%20PLOT%20CODE%2CT*FX%2C%28T-T*R%29*FY%5CnIF%20FX*FY%3D-1%20THEN%20MOVE%20T*FX%2CT*FY%20%3A%20MOVE%20T*FX%2C%28T-T*R%29*FY%20%3A%20PLOT%20CODE%2C%28T-T*R%29*FX%2CT*FY%5CnENDPROC%22%7D)

[Terminé noir et blanc](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE0%5CnS%3D128%5CnT%3DS%2F2%5CnFOR%20I%3D0%20TO%2010%5CnFOR%20J%3D0%20TO%208%5CnVDU%2029%2CI*S%3BJ*S%3B%5CnREM%20VDU%2029%2C640%3B512%3B%5CnA%3DRND%282%29%5CnIF%20A%3D1%20THEN%20FX%3D1%20%3A%20FY%3D1%20%3A%20PROCR%20%3A%20FX%3D-1%20%3A%20FY%3D-1%20%3A%20PROCR%5CnIF%20A%3D2%20THEN%20FX%3D-1%20%3A%20FY%3D1%20%3A%20PROCR%20%3A%20FX%3D1%20%3A%20FY%3D-1%20%3A%20PROCR%5CnNEXT%20J%5CnNEXT%20I%5CnEND%5CnDEF%20PROCR%5CnGCOL%200%2C1%20%3A%20PROCS%2811%2F8%2C%26B5%29%20%5CnGCOL%200%2C0%20%3A%20PROCS%284.5%2F8%2C%26B5%29%5CnENDPROC%5CnDEF%20PROCS%28R%2CCODE%29%5CnIF%20FX*FY%3D%201%20THEN%20MOVE%20T*FX%2CT*FY%20%3A%20MOVE%20%28T-T*R%29*FX%2CT*FY%20%3A%20PLOT%20CODE%2CT*FX%2C%28T-T*R%29*FY%5CnIF%20FX*FY%3D-1%20THEN%20MOVE%20T*FX%2CT*FY%20%3A%20MOVE%20T*FX%2C%28T-T*R%29*FY%20%3A%20PLOT%20CODE%2C%28T-T*R%29*FX%2CT*FY%5CnENDPROC%22%7D)
