---
layout: page
title: Publications
permalink: /publications/
---

See also my [DBLP page](https://dblp.org/pid/287/4919-1.html).

{% assign years = site.data.papers.papers | group_by: "year" %}
{% assign yearsSorted = years | sort: "name" | reverse %}

{% for year in yearsSorted %}
  <h3>{{ year.name }}</h3>

  <ul>
  {% for paper in year.items %}
    <li style="padding-bottom: 5pt;">
      {% for author_id in paper.authors %}
        {% assign author = site.data.people[author_id] %}
        {% if author.url %}
          <a href="{{ author.url }}">{{ author.name }}</a>
        {%- else %}
          {{ author.name }}
        {%- endif %}
        {%- if forloop.last != true %},{% endif %}
      {% endfor %}
      <br />
      <b><i>{{ paper.title }}</i></b> <br />
      {% for venue in paper.venues %}
        {{ venue.title }}
        {% if venue.link -%}
          [<a href="{{ venue.link }}">link</a>]
        {%- endif -%}
        {% if venue.comment %}
          ({{venue.comment}})
        {%- endif -%}
        {%- if forloop.last != true %},{% endif %}
      {% endfor %}
    </li>
  {% endfor %}
  </ul>
{% endfor %}
