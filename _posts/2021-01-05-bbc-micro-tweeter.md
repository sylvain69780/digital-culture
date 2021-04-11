---
layout: default
title: Jouer avec BBC micro Bot ! Analyse de 'devine nombre'.
tags: initiation
---
## Analyse d'un programme : devine nombre

Coller le programme ci-dessous dans le simulateur de BBC Micro. Peux-tu expliquer comment fonctione ce programme ? Quelle sont les variables utilisées ?

```basic
10 N=RND(9)
20 REPEAT 
25 CLS
30 PRINT "DEVINE LE NOMBRE AUQUEL JE PENSE"
30 PRINT "ENTRE 1 et 9"
40 R$ = GET$
45 R=VAL(R$)
50 PRINT "VOUS AVEZ DIT "; R ; "?"
55 IF R=0 THEN PRINT "REPONDEZ"
60 IF R>N THEN : PRINT "TROP GRAND"
70 IF R<N THEN : PRINT "TROP PETIT"
80 UNTIL N=R
90 PRINT "BRAVO C'EST BIEN " ; N ; " AUQUEL JE PENSAIS."
```

* Pourquoi le message "Devine ..." ne s'affiche pas ?
* Comment eviter que l'ecran s'efface à chaque réponse du coup on voit rien ?


[Simulateur d'Ordinateur BBC Micro](https://bbc.godbolt.org/)
