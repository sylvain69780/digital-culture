---
layout: default
title: Colorier des pixels
tags: initiation
---
:::warning
Pour commencer ce cours, il faut savoir que les couleurs affichées sur un écran d'ordinateur sont représentées par **3 valeurs numériques** :
C'est le codage **RGB** !

- Quantité de rouge (R Red en Anglais)
- Quantité de vert (G Green en Anglais)
- Quantité de bleu (B Blue en Anglais)
:::
# Etape 1 - Colorer un écran en **bleu**
- Aller sur le site https://www.shadertoy.com/
- Clique sur le bouton "Nouveau"
:::warning
:warning: 
En Anglais on ecrit les nombres à virgule avec un **point** et non pas une virgule.
Comme PI=3.1459 et non pas PI=3,14159
:warning: 
En language Shadertoy, Les valeures numériques comportent forcement un **point** (meme si il n'y a pas de chiffre après la virgule, c'est pour les distinger des valeurs entières)
:warning: 
Toutes les lignes de programme se terminent par un ";" pour les séparer les unes des autres.
:warning: 
Les lignes en commentaire (avec **//** au début de la ligne) ne sont pas executées par le programme. Ce sont des commentaires ! En mettant une ligne de programme en commentaire, on désactive celle-ci.
:::
- A la place (effacer et remplacer) de la ligne ci dessous
```cpp=
    // Time varying pixel color
    vec3 col = 0.5 + 0.5*cos(iTime+uv.xyx+vec3(0,2,4));
```
Taper 
```cpp=
    vec3 col = vec3(0.,0.,1.);
```
- Clique sur le bouton "Compiler" (play) en bas du programme, ou bien ALT+ENTER
- **Bravo** un écran bleu s'affiche. Vous avez affiché des pixels tout en bleu c'est très bien.
- Sauvez-vous afficher un écran en **rouge** ? En **vert** ? En **blanc** ? En **gris** (utiliser des valeurs décimales entre 0.0 et 1.0 comme 0.7 pour doser les couleurs)
:::success
Vous avez fait un programme sur Shadertoy :+1: 
:::
- **BONUS TIME** pour le plus rapides, affichez un dégradé de couleur en utilisant la variable **uv.y** à la place d'un des chiffres. **uv.y** C'est la hauteur du point à l'écran. **uv.x** c'est sa position horizontale à l'écran. On fait donc varier l'intensité de la couleur en fonction de la position du pixel à l'écran !

# Etape 2 - Modifier un programme Existant
- Aller sur le programme Walking Donut  du célèbre **Sylvain69780** https://www.shadertoy.com/view/tscfzs
- En début de programme, changez légèrement les valeurs ci-dessous et recompilez (ALT+ENTER). 
```cpp=
#define ITEMS_COUNT 12
#define DONUT_SIZE .12
```
- Que ce passe-t-il ? :bulb: Notez que ITEMS_COUNT est une valeure entière c'est pourquoi il ne faut pas de point ici !

- Aller à la ligne 315 et enlever le commentaire et compilez. Que ce passe-t-il ?
```cpp=
        c=vec3(0.,0.,1.);
```

- Pouvez-vous changer la couleur des Donuts en Jaune ?
- **BONUS TIME** pour le plus rapides
- Changez la vitesse de l'animation en modifiant ligne 179 le .5 par 0.2 par exemple 
```cpp=
    float time = iTime*.5;
```
-  Ligne 233, mettre en commentaire la ligne "sdCappedTorus" et décommentez une des lignes en dessous puis recompilez. Que ce passe-t-il ?
```cpp=
    float d = sdCappedTorus(q.zxy-vec3(0.,0.,0.0),vec2(sin(2.),cos(2.)),.4,DONUT_SIZE);
	// float d = sdTorus(q,vec2(.4,DONUT_SIZE));
    // float d = sdHexPrism(q.zxy,vec2(.4,DONUT_SIZE))-.02;
    // float d = sdOctahedron(q,.4); 
    // float d = length(q)-.4; // sphere
```
:::info
:bulb: 
- Un tore (Torus) est une forme de beignet
- Un Hexagone a six coté en colonne (HexPrism)
- Un Octahedre (Octahedron) a une forme de crystal.
- Une Sphere est une boule , replace le .4 par une nombre plus grand pour changer sa taille.
Tout ceci est expliqué par INIGO ici https://iquilezles.org/www/articles/distfunctions/distfunctions.htm
:::