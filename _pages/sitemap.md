---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: false
---

Een lijst met alle berichten en pagina's op NielsGouman.nl. Als je toevallig een robot bent kun je waarschijnlijk beter de [XML version]({{ "sitemap.xml" | absolute_url }}) versie checken.

## Pagina's
{% for post in site.pages %}
  {% include archive-single.html %}
{% endfor %}

## Berichten
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h2>{{ label }}</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}