---
layout: default
title: Experimenter en BBC Basic
tags: initiation
---
# BBC Microcomputer System - Guide Utilisateur

## Expérimenter
Vous êtes maintenant prêt à expérimenter. 
Préparez vous à voir ce que l'ordinateur peut faire, mais assurez-vous d'abord d'appuyer sur la touche BREAK (**F12** du simulateur).
Cela effacera l'écran et préparera l'ordinateur pour vous.
Tapez ce qui suit exactement comme indiqué:
`MODE 5`
puis appuyez sur la touche `ENTREE`. Comme vous le verrez, la commande `MODE 5` s'efface
l'écran et laisse simplement la marque `>` sur l'écran. `>` est appelé **invite**
et cela signifie que l'ordinateur est prêt pour votre prochaine commande.
Appuyer sur la touche `ENTREE` indique à l'ordinateur que vous avez terminé la ligne que vous tapez et que vous voulez qu'il obéisse à votre commande.
Avant d'appuyer sur la Touche `ENTREE` vous pouvez corriger les erreurs en appuyant sur la touche marquée `DELETE`.
Si l'ordinateur indique `Mistake`, appuyez sur la touche BREAK (**F12**) et réessayez,
en commençant par `MODE 5`.
Tapez ensuite chacune des lignes suivantes - mais n'oubliez pas d'appuyer sur `ENTREE`
touche à la fin de chaque ligne. 
Ne vous inquiétez pas si vous faites une erreur - ce n’est vraiment pas important !
```basic
DRAW 1000,100
DRAW 0,750
GCOL 0,1
PLOT 85,0,0
```
Si l'ordinateur affiche "No such variable" c'est que vous avez probablement tapé la lettre O au lieu du chiffre 0.

```basic
PLOT 86,1000,750
VDU 19,1,4,0,0,0
VDU 19,3,2,0,0,0
VDU 19,0,1,0,0,0
DRAW 200,0
DRAW 0,200
```
Comme vous pouvez le voir, la commande DRAW est utilisée pour dessiner des lignes, alors que `PLOT 85` et `PLOT 86` sont utilisés pour remplir des triangles à l'écran. Quand vous utiliser des graphiques, les points à l'écran sont numérotés de 0 à 1279 (de gauche à droite) et de 0 à 1023 (de bas en haut). 
Ce sont des positions comme sur une feuille de papier millimétré.

Les mots peuvent également être dessinés en couleur, comme vous avez pu le voir. Effacer l'écran en tapant `MODE 5` puis taper les commandes suivantes :


| |  |
| --------       | -------- | 
| `COLOUR 1`     | L'avant plan s'écrit en **rouge**.     | 
| `COLOUR 2`     | L'avant plan s'écrit en **jaune**. | 
| `COLOUR 3`     | L'avant plan s'écrit en **blanc**. | 
| `COLOUR 129`   | L'arrière plan s'écrit en **rouge**. | 
| `COLOUR 0`     | L'arrière plan s'écrit en **noir**. | 
| `COLOUR 130`   | L'arrière plan s'écrit en **jaune**. | 

Taper dans la console le programme ci-dessous

```basic
10 MODE 2
20 COLOUR RND(7)
30 PRINT "HELLO WORLD"
40 GOTO 20
```

## Les commandes

Il existe deux façons de faire faire quelque chose à l'ordinateur:
1. Donnez-lui des commandes sur lesquelles il peut agir immédiatement. C'est ce qui s'est passé
lorsque vous avez tapé les lignes du chapitre 1.
2. Donnez-lui une série d'instructions numérotées, souvent appelées instructions, qu'il peut
stocker dans sa mémoire et exécuter en séquence lorsqu'on lui demande de le faire. Une série stockée
d'instructions est appelé un programme.
De nombreux mots-clés de BASIC peuvent être utilisés à la fois comme commandes et comme
instructions dans un programme.
Le reste de ce chapitre concerne le «mode commande».
PRINT est utilisé pour que l'ordinateur imprime quelque chose sur l'écran. Essayez ces
deux exemples:
`PRINT "BONJOUR"`
N'oubliez pas d'appuyer sur RETURN à la fin de chaque ligne.
`PRINT 3 + 4`
Dans le deuxième exemple, vous avez donné à l'ordinateur une commande pour imprimer la somme
de 3 et 4. L'ordinateur peut très facilement faire l'addition, la soustraction, la multiplication
et la division. Les signes d'addition, de soustraction, de multiplication et de division sont
sur le côté droit du clavier. Si vous êtes intéressé à faire des mathématiques ou
travail financier, vous devrez alors connaître les symboles que l'ordinateur utilise pour
diverses opérations mathématiques. Ce sont:
```
+ Addition
- Subtraction
* Multiplication
\ Division
^ Exponentiation
. Decimal point
```
Si vous voulez obtenir le + ou *, vous devrez appuyer sur la touche SHIFT ainsi que
la clé que vous voulez. C'est un peu comme une machine à écrire: tout en maintenant la touche SHIFT
vers le bas, appuyez une fois sur le signe +.

Essayez de taper ce qui suit et vérifiez qu'ils fonctionnent - en d'autres termes, voyez que
ils produisent les réponses attendues.
```basic
PRINT 4 + 8
PRINT 18 - 2 * 4
PRINT 131/4
PRINT SQR(2)
```
Le dernier imprimera la racine carrée de 2 qui est 1,41421356.
Alors essaye
`MODE 5`
ce qui permettra à l'ordinateur d'effacer l'écran et de le préparer à dessiner des lignes ainsi que du texte. Dans ce mode
`COLOUR 129`
sélectionnera un fond rouge, et
`CLS`
effacera l'écran à la couleur d'arrière-plan. Dans chaque cas, vous avez donné le
ordinateur une commande et il y a obéi immédiatement. Travailler comme ça c'est appelé «travail en mode commande».

## Les variables

Dans le dernier chapitre, nous avons fait faire à l'ordinateur un certain nombre de calculs, mais c'était
je ne m'attendais pas à se souvenir des résultats après les avoir imprimés.
Supposons que vous deviez calculer les salaires de chacun dans une entreprise. 
Après vous avez calculé le salaire de chacun, il serait utile de pouvoir ajouter tous ensemble, de sorte qu'à la fin vous connaissez la masse salariale totale. En gardant le suivi des choses qui varient au cours d'un long calcul se fait à l'aide de variables.
Essayez de taper cette ligne sur l'ordinateur:
`LET Z=5`
Et maintenant, essayez de taper chacune des lignes suivantes:
```basic
PRINT Z+6
PRINT Z * 12
```
Comme vous l’avez vu, une fois que nous avons dit à l’ordinateur que «Z est 5», il comprend
que chaque fois que nous utilisons la lettre Z dans une somme, il faut jeter un œil pour savoir quelle est la valeur de Z (5 dans ce cas) et utiliser ce nombre dans l'arithmétique que nous lui attribuons. Tapez maintenant
`LET Z=7`
puis essayez ces deux lignes:
```basic
PRINT Z+12
PRINT Z/3
```
L’ordinateur est capable de stocker des centaines de variables différentes et les variables pas besoin d’appeler quelque chose d’aussi simple que Z; vous pouvez appeler une variable aussi longtemps qu'un nom que vous voulez.
Par exemple, vous pouvez taper
`MYAGE=30`
Notez que MYAGE a été écrit sans espaces entre le mot
variables:
1. Il ne doit y avoir aucun espace au milieu d'un nom de variable.
2. Tous les noms de variables doivent commencer par une lettre - cependant, vous pouvez ajouter autant de nombres que vous le souhaitez plus tard.
3. Vous ne devez pas utiliser de signes de ponctuation (tels que des points d'exclamation et des points d'interrogation) dans le nom de la variable, mais vous pouvez utiliser un caractère de soulignement.
4. Les noms de variables ne doivent pas commencer par des mots-clés BASIC tels que PRINT et LET.

Pour afficher des caractères minuscules à l'écran, assurez-vous que le VERROU MAJUSCULE est
éteignez-le en appuyant dessus pour éteindre sa lumière. Maintenant, vous obtiendrez de petites lettres et des chiffres.
Maintenez la touche SHIFT enfoncée si vous souhaitez utiliser des majuscules avec des lettres minuscules.
Tous les noms de variables suivants sont acceptables.
```basic
LET AGE=38
LET this year=1984
LET lengthOFrod=18
LET CAR_mileage=13280
LET value5=16.1
LET weight4=0.00135
LET chicken2egg3=51.6
```
Cependant, les noms de variables suivants sont illégaux.
```basic
LET Football Result=3 (There’s a space.)
LET Who?=6 (There’s a question mark.)
LET 4thvalue=16.3 (Starts with a number.)
LET TODAY=23 (Starts with TO.)
LET PRINT=1234.56 (PRINT is a reserved word.)
```
Vous remarquerez que dans tous les exemples ci-dessus, nous avons mis le mot LET avant
le nom de la variable. Cela donne une indication claire de ce qui se passe réellement
à l'intérieur de l'ordinateur, à savoir que la variable numérique this_year, dans l'un des
exemples, reçoit une nouvelle valeur «1984». Le mot LET est facultatif et le
l'ordinateur acceptera également
`this_year=1984`
Cette version abrégée est plus fréquemment utilisée.

## Un programme simple

Dans le chapitre précédent, nous avons donné les commandes informatiques qu'il obéit immédiatement. Le problème avec cette technique est qu'il faut attendre jusqu'à ce que l'ordinateur ait terminé une commande avant de pouvoir lui donner la suivante. 
Le même problème se pose lorsque vous emmenez une voiture dans un garage pour y être réparée.
Vous pouvez par exemple rester à côté du mécanicien et dire: «Tout d’abord, je veux de l’huile et vous pourriez alors attendre qu’il change l’huile. Quand c'est terminé, vous pouvez alors dire "Maintenant, je veux que vous remplaciez l'ampoule qui a grillé dans l’un des phares avant », puis vous pourriez attendre que ce travail soit fait.
Et troisièmement, vous pourriez dire: «L’échappement fait du bruit, alors je veux que vous mettiez la voiture sur la rampe et vérifiez-la ».
Vous passeriez beaucoup de temps à attendre que le mécanicien termine chaque
travail avant d'attribuer le suivant. Il existe une manière beaucoup plus efficace de faire les choses;
lorsque vous entrez dans le garage, vous donnez au mécanicien tout un ensemble d'instructions, pour
exemple:
- Commencez par changer l'huile.
- Remplacez ensuite l'ampoule du phare.
- Troisièmement, arrêtez le bruit dans l'échappement.
Une fois que vous avez donné votre ensemble d'instructions et vérifié que le garage comprend ce qui doit être fait, vous pouvez partir et prendre une tasse de café et puis revenez en attendant que le travail soit terminé. Maintenant, la même chose s'applique avec un ordinateur. Il est de loin préférable de lui donner un ensemble d'instructions et de le laisser fonctionner pendant que vous vous éloignez et prenez une tasse de café. «Ecrire un programme informatique» n’est rien plus que de donner un ensemble d'instructions.
Si vous donnez à l'ordinateur une commande comme
PRINT "HOW ARE YOU"
alors l'ordinateur le fera immédiatement. D'un autre côté, si vous donnez une déclaration à l'ordinateur
```basic
10 PRINT "HOW ARE YOU"
```
alors l'ordinateur considérera cela comme l'instruction numéro 10 et il ne le fera pas immédiatement, mais s'attend à ce que d'autres instructions suivent. L'instruction numéro 10 est généralement appelée ligne 10. Encore une fois: s'il y a un numéro de ligne, l'instruction
fait partie d'un programme; s'il n'y a pas de numéro de ligne, c'est une commande à laquelle l'ordinateur doit obéir immédiatement.
Lorsque vous avez donné à l'ordinateur un ensemble d'instructions et que vous voulez qu'il les exécute, vous tapez le mot RUN sur le clavier. L'ordinateur exécutera alors les instructions que vous lui avez demandées de faire une par une et dans l'ordre des numéros de ligne. En d'autres termes, il «exécutera» le programme que vous avez tapé. Juste pour vérifier que vous avez une idée de ce qui se passe, voici un petit programme que vous pouvez taper.
```basic
10 REPEAT
20 PRINT "DONNE-MOI UN NUMERO";
30 INPUT B
40 PRINT "12 FOIS ";B;" VAUT ";12*B
50 UNTIL B=0
```
Lorsque vous exécutez la ligne de programme 20 imprimera le message
`DONNE-MOI UN NUMERO`
sur l'écran.
La ligne 30 imprimera un point d'interrogation à l'écran et attendra que vous saisissiez un nombre (suivi de RETOUR - comme d'habitude). Le nombre que vous saisissez deviendra la valeur de la variable «B».
La ligne 40 imprimera d'abord les mots 12 FOIS suivis sur la même ligne du
numéro que vous avez tapé, suivi sur la même ligne du mot IS suivi du
résultat du calcul. Les points-virgules indiquent à l'ordinateur d'imprimer l'élément suivant sur la même ligne que le précédent et juste en face.
La ligne 50 renvoie l'ordinateur à la ligne 10 sauf si B = 0, alors le programme s'arrête.
Une autre façon d'arrêter le programme est d'appuyer sur le «bouton panique» qui est marqué ÉCHAPPEMENT (il se trouve en haut à gauche du clavier). 
Si l'ordinateur semble vous ignorer parce qu'il est trop occupé à exécuter un programme. Vous pouvez presque toujours attirer son attention en appuyant sur la touche ÉCHAPPEMENT. Lorsque vous faites cela, il arrêtera d'exécuter votre programme et affichera une invite> pour montrer qu'il a arrêté le programme et qu'il attend votre commande.
Lorsque l'ordinateur affiche un>, il est en mode commande. Vous pouvez changer votre programme, donnez-lui des commandes pour une exécution immédiate, ou dites-lui d'exécuter le programme (dans sa mémoire) à nouveau. Il n’oublie pas un programme lorsque vous appuyez sur ÉCHAPPER.

Si l'ordinateur est en mode commande (en d'autres termes si la dernière chose sur le est>) alors vous pouvez lui commander d'imprimer le programme dans sa mémoire en tapant
`LIST`
et en appuyant sur ENTREE.
L'ordinateur affichera alors une liste du programme à l'écran pour que vous
joue. Si vous découvrez que vous avez fait une erreur, par exemple que vous avez quelque chose ne va pas à la ligne 20, alors il est facile de corriger l'erreur. Il y en a deux moyens de corriger les erreurs majeures:
- Retapez toute la ligne.
- Utilisez l'éditeur d'écran.

[La suite du manuel Anglais](http://bbc.nvg.org/doc/BBCUserGuide-1.00.pdf)

