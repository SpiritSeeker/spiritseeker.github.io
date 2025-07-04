---
layout: single
title: "Publications"
permalink: /publications/
---


{% assign pubs_by_year = site.data.publications | group_by: "year" | sort: "name" | reverse %}

{% for year_group in pubs_by_year %}
## {{ year_group.name }}

<ul style="font-size: 0.9rem; line-height: 1.4;">
  {% for pub in year_group.items %}
    <li style="margin-bottom: 1.2em;">
      {{ pub.author }}, "{{ pub.title }}," <em>{{ pub.booktitle }}</em>,
      {% if pub.volume %}vol. {{ pub.volume }}, {% endif %}
      {% if pub.number %}no. {{ pub.number }}, {% endif %}
      {% if pub.pages %}pp. {{ pub.pages }}, {% endif %}
      {% if pub.year %}{{ pub.year }}.{% else %}n.d.{% endif %}
      {% if pub.url %}
        [<a href="{{ pub.url }}" target="_blank" rel="noopener noreferrer">Read here</a>]
      {% endif %}
      {% if pub.doi %}
        [DOI: <a href="https://doi.org/{{ pub.doi }}">{{ pub.doi }}</a>]
      {% endif %}
    </li>
  {% endfor %}
</ul>

{% endfor %}
