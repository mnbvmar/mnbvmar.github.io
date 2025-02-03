---
layout: page
title: Teaching
permalink: /teaching/
---

All of the courses below were taught at the University of Warsaw.

<ul>
  {% for course in site.data.teaching.courses %}
  <li style="padding-top: 1em;">
    <img src="{{ site.baseurl }}/assets/img/lang-{{ course.lang }}.png" style="border: 1px solid gray;">
    <b>{{ course.name }}</b> {{ course.type }} ({{ course.year }}) <br />
    {% for link in course.links %}
      <i>{{ link.name }}</i>: [<a href="{{ link.url }}">link</a>] <br />
    {% endfor %}
  </li>
  {% endfor %}
</ul>
