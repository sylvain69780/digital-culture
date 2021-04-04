---
layout: default
---
# A propos

Quelques ressources pour s'initier à l'informatique.
Des ateliers de 1 heure maximum.

# Posts 

{% for tag in site.tags %}
  <h2>{{ tag[0] }}</h2>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.date | date: "%Y-%m-%d" }} {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
