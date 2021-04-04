---
layout: default
title: Creer un Blog avec GitHub pages
tags: initiation
---

Il est facile de créer un Blog avec GitHub pages.

Simplement 
* créer un repository, et activer GitHub pages sur la branch "main".
* Respected l'arborescence décrite [ici](https://jekyllrb.com/docs/structure/)

Pour qu'un fichier md ou html soit traité par Jekyll, il doit avoir au début 
```
---
layout: page
title: About
---
```

* Le langage utilisé dans les pages et "Liquid" dont la documentation est [ici](https://jekyllrb.com/docs/liquid/)

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