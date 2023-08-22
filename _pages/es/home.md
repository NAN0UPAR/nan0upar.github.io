---
title: "Home"
layout: homelay
sitemap: false
permalink: /es/home
redirect_from: 
  - /es
  - /
lang: es
ref: home
---

{% for item in site.data.global.t[page.lang].navbar %}
  {% if item.url contains 'papers' %}
    {% assign moreworks_url = item.url %}
  {% endif %}
  {% if item.url contains 'news' %}
    {% assign morenews_url = item.url %}
  {% endif %}
{%endfor%}

{% for home_content in site.data.contents.content_home.t[page.lang] %}

## {{ home_content.title }}

{{ home_content.text}}

{% contentfor openings %}
__¿Vacantes? Visita [esta página]({{ site.url }}{{ site.baseurl }}/vacancies.html) si estás interesado en unirte a nuestro grupo.__
{% endcontentfor %}

{% contentfor exampleswork %}
## Ejemplo de nuestro trabajo
{{ home_content.works }}
{% endcontentfor %}

{% endfor %}


{% contentfor moreworks %}
##### [... ver todos los trabajos]({{ site.url }}{{ site.baseurl }}/{{ moreworks_url }})
{% endcontentfor %}



{% contentfor news %}
## Noticias
  {% for article in site.data.news limit:10%}
    <b>{{ article.date }}</b>
    {{ article.headline }}
    {% endfor %}
{% endcontentfor %}

{% contentfor morenews %}
##### [... ver todas las noticias]({{ site.url }}{{ site.baseurl }}/{{ morenews_url }})
{% endcontentfor %}