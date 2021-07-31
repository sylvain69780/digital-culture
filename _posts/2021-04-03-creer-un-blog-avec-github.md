---
layout: default
title: Creer un Blog avec GitHub pages
tags: initiation
---

# Introduction

Comment faire pour épater ses copains/copines, parents, cousins ?
Il faut savoir faire des choses et le montrer !
Il faut aussi pour pouvoir bien expliquer quelque chose, l'avoir écrit quelque part correctement.
Sur un blog, on se présente et on publie des articles sur les sujets qu'on souhaite, ceux qui nous font plaisir, ce qui nous interesse.

Sur un blog, tout est absoluemnet public, il faut donc **prendre soin de bien expliquer** pour qu'un étranger puisse comprendre.
Il ne faut pas non plus mettre des informations trop personnelles qui pourraient être mal utilisées, il ne faut pas mettre de 
contenu offensant, et ne pas utiliser des contenus soumis à des droits d'auteur.

Pourquoi cela ?

Concernant l'orthographe, ce n'est pas le plus important, sauf si on fait un blog justement sur l'orthographe !
Passer un peu de temps tout de même à se relire pour éviter les remarques idiotes.

# Découverte

Il est facile de créer un Blog avec GitHub pages.

Simplement 
* créer un repository, et activer GitHub pages sur la branch "main".
* Respected l'arborescence décrite [ici](https://jekyllrb.com/docs/structure/)

Pour qu'un fichier md ou html soit traité par Jekyll, il doit avoir au début 
```
---
layout: default
title: About
---
```

* Le langage utilisé dans les pages est "Liquid" dont la documentation est [ici](https://jekyllrb.com/docs/liquid/)

On va peut l'utiliser mais c'est bien pratique pour lister les posts.

Example de code "Liquid" :

Pour afficher la liste des posts groupés par Tag : 
{% raw %}
```
{% for tag in site.tags %}
  <h2>{{ tag[0] }}</h2>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.date | date: "%Y-%m-%d" }} {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
```
{% endraw %}

Pour afficher tous les posts

{% raw %}
```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```
{% endraw %}

# Se présenter / publier un article

[OpenClassrooms](https://openclassrooms.com/fr/courses/1304236-redigez-en-markdown)

 [Blog de Damien](https://damii-en.github.io/)  

 [Blog de Marion](https://marionchampi.github.io/)
 

Publier une image
Publier un lien
Mettre en forme avec Markdown

