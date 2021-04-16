---
layout: default
title: Jouer avec BBC micro Bot ! Color cycling.
tags: initiation
---
## La programmation créative

Les ordinateurs servent à beaucoup de choses aujourd'hui.
Ils servent à faire des jeux bien sûr, on peut faire son travail sur des ordinateurs qui comptent l'agent qu'on a en banque par exemple, mais pour s'amuser on peut aussi faire de la programmation créative en jouant avec nos sens de la vue (dessiner, animer), en utilisant différentes techniques.

Vous aller faire une animation en utilisant la technique du cyclage des couleurs.
Nous allons dessiner un traits à différentes positions de l'écran, chaque fois d'une couleur différente (1 à 15), puis l'animer en ne rendant visible qu'une couleur à la fois.

1. Ouvrir l'editeur [BBC Basic](https://bbcmic.ro/) et Ouvir [Page d'aide de Owlet Editor](http://translate.google.com/translate?sl=en&tl=fr&u=https://www.bbcmicrobot.com/learn/index.html) ainsi que la [Page de Paul MALIN](https://translate.google.com/translate?hl=&sl=en&tl=fr&u=https%3A%2F%2Fblog.mousefingers.com%2Fpost%2Fbbc%2Fbbc_colour_cycling%2F&sandbox=1) qui parle de la technique de cyclage des couleurs.
2.  Expliquer ce que sont les couleurs "logiques" et les couleurs "physiques"
3. Faire un test avec ```VDU 19,L,P,0,0,0``` en choisissant la couleur L (logique) à remplacer par la couleur P (physique).
4. Modifiez votre programme de la semaine dernière pour tracer des lignes colorées de 1 en 1 et paralleles. 
5. Faire que la couleur augmente de 1 à chaque dessin.
6. Placer le code de Paul Malin à la fin du programme pour le cyclage de couleurs et faire l'animation. 
```
K=1 : REM logical colour to keep 
FOR L=1 TO 15 : REM Only set 1-15, leave 0 as black
P=4 : REM physical colour to set
IF L=K THEN P=5 : REM set physical colour to magenta
VDU 19,L,P,0,0,0
NEXT L
K=K+1
IF K>15 THEN K=1
```  
7. Poster voter Creation sur Tweeter

