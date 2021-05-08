---
layout: default
title: Les chaines de caractères
tags: initiation
---
# Introduction

Vous devez faire vos preuves auprès de Sébastien Truchet si vous voulez qu'il vous confie la réalisation de sa prochaine oeuvre.

Il veut s'assurer que vous savez correctement taper au clavier.

Il faut ensuite lui prouver que vous savez vos tables de multiplication, en les faisant afficher par un programme.

# Echauffement

[Réaliser les exercices](https://www.typingclub.com/dactylographie)

>Avancer le plus possible dans les excercices en 20 minutes
>On fera au moins 20 minutes de cette exercice à chaque fois.

# Realiser l'exercice de programmation

- On va utiliser le MODE 0
- Definir une variable T=7 pour afficher la table de 7
- Vous pouvez choisir d'afficher la table de 7 de 3 façons différentes
    - En multipliant le compteur de boucle par T
    - En utilisant une variable a laquelle on ajoute T à chaque tour de boucle
    - En utilisant le mot clé STEP de la boucle FOR
- Sebastien Truchet souhaite voir appraitre les nombres sur une seule ligne, séparés par des espaces.
    - Definir ```L$="Table de "+STR$(T)+" :"``` Au debut du programme        
    - Les variable avec un $ à la fin sont utilisés pour memorier des chaines de caratères. On dit toujours qu'on ne peut pas mélanger les choux et les carottes donc il faut bien pouvoir les reconnaitre.
    - Jusqu'ici on avait utilisé que les variables numeriques, vous devez lire la page [sur les chaines](https://www.bbcbasic.co.uk/bbcwin/tutorial/chapter06.html) 
    - A quoi sert la fonction STR$ ?
    - Le resultat final doit êter : ```Table de 7 : 1x7=7 2*7=14 3*7=21 ... 9x7=63```
- Finalement : Definir une boucle pour faire varier T de 1 à 9 et donc afficher toutes les tables de multiplication.

**Liens utiles**
- [BBC Basic Editor](https://bbcmic.ro/)
- [Page d'exemples de boucles FOR](http://www.bbcbasic.co.uk/bbcwin/tutorial/chapter11.html)

