---
title: "Home"
layout: homelay
sitemap: false
permalink: /en/home
redirect_from: 
  - /en
lang: en
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
__Openings? Visit [this page]({{ site.url }}{{ site.baseurl }}/vacancies.html) if you're interested in joining our group.__
{% endcontentfor %}

{% contentfor exampleswork %}
## Examples of our work

{{ home_content.works }}
{% endcontentfor %}

{% endfor %}


{% contentfor moreworks %}
##### [... see all works]({{ site.url }}{{ site.baseurl }}/{{ moreworks_url }})
{% endcontentfor %}



{% contentfor news %}
## News
  {% for article in site.data.news limit:10%}
    <b>{{ article.date }}</b>
    {{ article.headline }}
    {% endfor %}
{% endcontentfor %}

{% contentfor morenews %}
##### [... see all news]({{ site.url }}{{ site.baseurl }}/{{ morenews_url }})
{% endcontentfor %}