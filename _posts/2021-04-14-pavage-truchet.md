---
layout: default
title: BBC micro bot, truchet
tags: initiation
---
# Intro

Avant d'aller plus loin, on va revoir ce qu'on a fait la dernière fois

On va faire un nouveau pavage carré, mais varié

[Sebastien Truchet](https://fr.wikipedia.org/wiki/S%C3%A9bastien_Truchet) inventeur de ces pavages, est né à Lyon en 1657 ! Il ne pensait pas qu'on allait encore parler de lui 360 ans plus tard. Bravo Sébastien !

A vous de jouer maintenant, je compte sur vous pour que je puisse décorer mon blog de vos meilleures creations.

# Les liens utiles

Utiliser la traduction automatique en Francais disponible dans Chrome

En echauffement, commencer par afficher les nombres de 0 à 6, tous dans une couleur differente.
Couleur de texte : utilisaton de la fonction COLOUR

- [BBC Basic Editor](https://bbcmic.ro/)
- [La page d'aide en Anglais de Dominic Pajak le createur du BBC micro bot](https://www.bbcmicrobot.com/learn/index.html)
- [La page de Paul Malin sur les fonctions graphiques](https://blog.mousefingers.com/post/bbc/bbc_reference/)

- [ROM d'extension](file:///C:/Users/sylvain.lecourtois/Downloads/Graphics_Extension_ROM%20(1).pdf)

# Etapes

Utiliser les exemples ci-dessous, mais pas de couper coller

- [Dessiner un CARRE de taille S centré à l'écran](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D128%5CnVDU%2029%2C640%3B512%3B%5CnMOVE%200%2C0%5CnPLOT%20153%2C100%2C0%5Cn%22%7D)

La commande ci-dessous permet de redefinir l'origine 0,0 du repere de l'ecran, ce qui est bien pratique.

```basic
VDU 29,640;512;
```

- [Dessiner les lignes qui rejoignent les centres des cotes](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D256%5CnVDU%2029%2C640%3B512%3B%5CnT%3DS%2F2%5CnMOVE%20T%2CT%5CnDRAW%20-T%2CT%5CnDRAW%20-T%2C-T%5CnDRAW%20T%2C-T%5CnDRAW%20T%2CT%5Cn%5Cn%22%7D)
- [Solution](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D256%5CnVDU%2029%2C640%3B512%3B%5CnT%3DS%2F2%5CnMOVE%20T%2CT%5CnDRAW%20-T%2CT%5CnDRAW%20-T%2C-T%5CnDRAW%20T%2C-T%5CnDRAW%20T%2CT%5CnMOVE%200%2CT%5CnDRAW%20-T%2C0%5CnDRAW%200%2C-T%5CnDRAW%20T%2C0%5CnDRAW%200%2CT%5Cn%5Cn%22%7D)

- [Pavage truchet simple](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D128%5CnFOR%20I%20%3D%200%20TO%2010%20%5CnFOR%20J%20%3D%200%20TO%209%20%5CnVDU%2029%2CI*S%3BJ*S%3B%5CnPROCCARRE%5CnNEXT%20J%5CnNEXT%20I%5CnEND%5CnDEF%20PROCCARRE%5CnT%3DS%2F2%5CnR%3DINT%28RND%281%29*2%29%5CnIF%20R%3D1%20THEN%20MOVE%200%2CT%20%3A%20DRAW%20-T%2C0%20%5CnIF%20R%3D0%20THEN%20MOVE%20-T%2C0%3A%20DRAW%200%2C-T%5CnIF%20R%3D1%20THEN%20MOVE%200%2C-T%20%3A%20DRAW%20T%2C0%5CnIF%20R%3D0%20THEN%20MOVE%20T%2C0%20%3A%20DRAW%200%2CT%5CnENDPROC%22%7D)

- [Pavage truchet arcs de cercle](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D128%5CnFOR%20I%20%3D%200%20TO%2010%20%5CnFOR%20J%20%3D%200%20TO%209%20%5CnVDU%2029%2CI*S%3BJ*S%3B%5CnPROCCARRE%5CnNEXT%20J%5CnNEXT%20I%5CnEND%5CnDEF%20PROCCARRE%5CnT%3DS%2F2%5CnR%3DINT%28RND%281%29*2%29%5CnIF%20R%3D0%20THEN%20MOVE%20T%2C-T%20%3A%20MOVE%20T%2C0%20%3A%20PLOT%20%26A5%2C0%2C-T%5CnIF%20R%3D0%20THEN%20MOVE%20-T%2CT%20%3A%20MOVE%20-T%2C0%20%3A%20PLOT%20%26A5%2C0%2CT%5CnIF%20R%3D1%20THEN%20MOVE%20T%2CT%20%3A%20MOVE%200%2CT%20%3A%20PLOT%20%26A5%2CT%2C0%5CnIF%20R%3D1%20THEN%20MOVE%20-T%2C-T%20%3A%20MOVE%200%2C-T%20%3A%20PLOT%20%26A5%2C-T%2C0%5CnENDPROC%22%7D)

- [Remplissage du motif](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnS%3D128%5CnFOR%20I%20%3D%200%20TO%2010%20%5CnFOR%20J%20%3D%200%20TO%209%20%5CnVDU%2029%2CI*S%3BJ*S%3B%5CnPROCCARRE%5CnNEXT%20J%5CnNEXT%20I%5CnFOR%20I%20%3D%200%20TO%2010%20%5CnFOR%20J%20%3D%200%20TO%209%20%5CnVDU%2029%2CI*S%3BJ*S%3B%5CnGCOL%200%2CINT%28RND%285%29%2B1%29%5CnPLOT%20%2685%2CS%2F2%2CS%2F2%5CnNEXT%20J%5CnNEXT%20I%5CnEND%5CnDEF%20PROCCARRE%5CnT%3DS%2F2%5CnR%3DINT%28RND%281%29*2%29%5CnIF%20R%3D0%20THEN%20MOVE%20T%2C-T%20%3A%20MOVE%20T%2C0%20%3A%20PLOT%20%26A5%2C0%2C-T%5CnIF%20R%3D0%20THEN%20MOVE%20-T%2CT%20%3A%20MOVE%20-T%2C0%20%3A%20PLOT%20%26A5%2C0%2CT%5CnIF%20R%3D1%20THEN%20MOVE%20T%2CT%20%3A%20MOVE%200%2CT%20%3A%20PLOT%20%26A5%2CT%2C0%5CnIF%20R%3D1%20THEN%20MOVE%20-T%2C-T%20%3A%20MOVE%200%2C-T%20%3A%20PLOT%20%26A5%2C-T%2C0%5CnENDPROC%22%7D)


# Resultats

[Marion](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE%200%5CnS%3D100%5CnT%3DS%2F2%5CnFOR%20Z%3D0%20TO%2011%5CnFOR%20Y%3D0%20TO%2010%5CnR%3DRND%281%29%5CnVDU%2029%2CZ*S%3BY*S%3B%5CnIF%20R%3E0.5%20THEN%20MOVE%200%2CT%20%3A%20DRAW%20T%2C0%5CnIF%20R%3E0.5%20THEN%20MOVE%20-T%2C0%20%3A%20DRAW%200%2C-T%5CnIF%20R%3C%3D0.5%20THEN%20MOVE%200%2C-T%20%3A%20DRAW%20%20T%2C0%5CnIF%20R%3C%3D0.5%20THEN%20MOVE%20-T%2C0%20%3A%20DRAW%200%2CT%5CnNEXT%20Y%5CnNEXT%20Z%5CnPLOT%20%2685%2C0%2C0%22%7D)

![Image]({{ site.baseurl }}\assets\images\truchet2_marion.png)

[Damien](https://bbcmic.ro/#%7B%22v%22%3A1%2C%22program%22%3A%22MODE2%5CnGCOL%200%2C15%5CnS%3D128%5Cnpoo%3DS%2F2%5CnFOR%20cnul%3D%200%20TO%2011%5CnFOR%20y%3D%200%20TO%2010%5Cnnon%3D%20RND%281%29%5CnVDU%2029%2Ccnul*S%3By*S%3B%5CnIF%20non%3E0.5%20THEN%20MOVE%200%2Cpoo%3ADRAW%20poo%2C0%5CnIF%20non%3C0.5%20THEN%20MOVE%20poo%2C0%3ADRAW%200%2C-poo%5CnIF%20non%3E0.5%20THEN%20MOVE%20-poo%2C0%3ADRAW%200%2C-poo%5CnIF%20non%3C0.5%20THEN%20MOVE%20-poo%2C0%3ADRAW%200%2Cpoo%5CnNEXT%20y%5CnNEXT%20cnul%5CnMOVE%200%2C0%5CnVDU%2029%2C0%3B0%3B%5CnGCOL%200%2C8%5CnPLOT%20%2685%2C0%2C0%5CnPLOT%20%2685%2C1000%2C1000%5CnPLOT%20%2685%2C1000%2C0%5CnPLOT%20%2685%2C0%2C1000%5CnPLOT%20%2685%2C200%2C500%22%7D)

![Image]({{ site.baseurl }}\assets\images\truchet2_damien.png)
