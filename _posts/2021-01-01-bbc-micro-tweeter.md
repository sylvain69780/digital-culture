---
layout: default
title: Jouer avec BBC micro Bot ! Tweeter ses creations.
tags: initiation
---
## Programmer en BASIC

Nous allons maintenant apprendre les modes graphiques en utilisant le simulateur BBC Micro

### Les modes graphiques

Vous allez trouver la réponse aux questons ci-dessous dans la page (a traduire avec Google translate) ci-dessous 

[fun with BBC micro](https://blog.mousefingers.com/post/bbc/bbc_bbcmicrobot/)

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
