---
layout: page
title: Team
permalink: /team/
---

These are the people who organise UK AI.

<ul>
{%- for person in site.data.team -%}
  <li><a href="{{ person.url }}">{{ person.name }}</a>, {{ person.affiliation }}</li>
{%- endfor -%}
</ul>
