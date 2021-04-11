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

## Un autre type de boucle : REPEAT ... UNTIL (Fait le 6 mars 2021) 

Faire un programme qui simule le lancement d'une fusée. Le programme s'arrête lorsque la fusée touche le sol.

* Données du problème
    * X va de 0 à 1279 , Y de 0 à 1023.
    * Postion de départ de la fusée en bas au centre de l'ecran
    * Vitesse initiale de la fusée VY=10 et VX=5
    * Decroissance de la vitesse horizontale VY à cause de la gravite A=-1

1. Ouvrir l'editeur [BBC Basic](https://bbcmic.ro/)
2. Choisir son mode Graphique dans [Page de Paul MALIN](https://translate.google.com/translate?sl=en&tl=fr&u=https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)
3. La position de départ de la fusée sera en bas a gauche de l'écran. (creer les variables ``` X=0``` ,``` Y=0``` )
4. La vitesse horizontale de la fusée sera de 5 et la vitesse verticale 10. Definir ``` VX=5```  et ``` VY=10``` 
5. La pesanteur va faire diminuer la vitesse horizontale de 0.1 à chaque fois, definir ``` A=0.1``` 
6. Positionez la fusee sur son lieu de lancement ```MOVE X,Y``` 
7. On calcule la nouvelle position de la fusee, la nouvelle vitesse horizontale.
8. La trajectoire de la fusée sera représentée par une ligne qu'on va tracer avec ```DRAW X,Y``` 
9. Boucler jusqu'à que que la fusée touche le sol ```REPEAT ... UNTIL Y<=0``` et afficher "TERMINE" à la fin.
10. Lancer des fusées aléatoirement
11. Donner une couleur aleatoire à chaque trajectoire.
12. Tweeter votre création.

**Marion**
```basic
MODE 2
FOR B=0 TO 3
X=0
Y=0
VX=5+RND(150)/10
VY=10+RND(150)/10
A=0.1
MOVE X,Y
REPEAT
GCOL 0,5+RND(15)
X=X+VX
Y=Y+VY
VY=VY-A
DRAW X,Y
UNTIL Y<=0
COLOUR 11
NEXT B
PRINT "END"
```
**Damien**
```basic
MODE2
FOR j=0 TO 3
GCOL 0,RND(15)
x=0 
y=0
vx=5
vy=5 + RND(10*10)/10
a=0.1
MOVE x,y
REPEAT
vy=vy-a
x=vx+x
y=vy+y
DRAW x,y
UNTIL y<=0
COLOUR 8
NEXT j
PRINT "terminus"
```


## Toujours plus de boucles (fait le 27 février)
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


## Programmer en basic, Un programme plus compliqué (fait le 13 février)

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

## Programmer en BASIC (Fait)

Nous allons maintenant apprendre les modes graphiques en utilisant le simulateur BBC Micro

### Les modes graphiques

Vous allez trouver la réponse aux questons ci-dessous dans la page traduite ci-dessous [Traduction Google](https://translate.google.com/translate?sl=en&tl=fr&u=https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)

Commandes graphiques : Modes graphiques

* Comment change-t-on de mode graphique ?
* Quel de le mode graphique qui a la meilleur definition d'image ?
* Quel est le mode avec le plus de couleurs possibles ?

Lancer le simulateur

[Simulateur d'Ordinateur BBC Micro](https://bbc.godbolt.org/)

* Passer en mode 0 et tracer une ligne du centre de l'écran au coin en bas à gauche de l'écran.

Les différents modes graphiques ont des résolutions différentes mais quelle que soit la résolution, les commandes graphiques utilisent des coordonnées de dessin avec une plage de 0-> 1279 en X et 0-> 1023 en Y.

Faire un brouillon papier de votre dession à base de lignes et de ronds qu'on va réaliser.

Nous allons utiliser maintenant un outil plus pratique pour faire notre programme en BASIC de 1981
[Lien vers l'éditeur en ligne](https://bbcmic.ro/)
Control+ENTREE execute le programme !

Et une fois notre programme au point, nous allons le poster à un Robot sur tweeter qui va l'executer et nous répondre !

Lire les parties 

* Graphics Modes
* Drawing Commands
* Graphics Extension ROM Drawing Commands
* Colour

Tweeter notre oeuvre d'art !

```basic 
MODE 0
FOR I=0 TO 40
PRINT I
NEXT I
```

Ignored tweets
The bot will reply to any mention that starts with a line number, contains an = sign or contains special characters. This needs improving.

Tweets ignorés
Le bot répondra à toute mention commençant par un numéro de ligne, contenant un signe = ou contenant des caractères spéciaux. 
