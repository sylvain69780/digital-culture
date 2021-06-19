---
layout: default
---
# A propos

Quelques ressources pour s'initier à l'informatique.
Des ateliers de 1 heure maximum.

Je met en garde les personnes qui comme moi voudraient interesser leurs enfants à la creation artistique sur ordinateur. Le sujet doit être amené avec une vraie approche pédagogique, sans cela l'echec est assuré.

Pour savoir ce qu'est une séquence pédagogique voici la page Wikipedia : [Séquence pédagogique](https://fr.wikipedia.org/wiki/S%C3%A9quence_p%C3%A9dagogique#:~:text=La%20s%C3%A9quence%20p%C3%A9dagogique%20(appel%C3%A9e%20aussi,variable%2C%20r%C3%A9parties%20dans%20le%20temps.)

# Posts 

{% for tag in site.tags %}
  <h2>{{ tag[0] }}</h2>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.date | date: "%Y-%m-%d" }} {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
