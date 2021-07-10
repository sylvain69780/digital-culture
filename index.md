---
layout: default
---
# A propos

Quelques ressources pour s'initier à l'informatique.
Des ateliers de 1 heure maximum.

Je met en garde les personnes qui comme moi voudraient interesser leurs enfants à la creation artistique sur ordinateur. Le sujet doit être amené avec une vraie approche pédagogique, sans cela l'echec est assuré.

[Principes généraux pour mener
une séquence d'apprentissage](http://www.ac-grenoble.fr/ien.grenoble5/IMG/pdf_Sequence_d_apprentissage-2.pdf)

# Posts 

{% for tag in site.tags %}
  <h2>{{ tag[0] }}</h2>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.date | date: "%Y-%m-%d" }} {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
