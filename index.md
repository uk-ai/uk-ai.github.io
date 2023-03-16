---
layout: default
title: Home
---

We organise meetings where UK AI researchers gather to share their ideas. The next meeting will be held in 2023. Details can be found [on this page](https://uk-ai.org/ukai2023/).

<h3>Upcoming Meetings</h3>

<ul>
{%- assign sorted = site.github.public_repositories | sort: 'created_date' -%}
{%- for repository in sorted reversed -%}{%- if repository.has_pages -%}{%- unless repository.name contains 'github.io' -%}
  {% assign firstletter = repository.name | slice: 0, 2 %}
    {%-if firstletter=='e-' and unless repository.description contains '(previous)'-%}
    <li>
    <a href="{{ repository.name | prepend: site.baseurlsite }}"><b>{{ repository.description }}</b></a>
    </li>
    {%-endif-%}
  {%- endunless -%}{%- endif -%}{%- endfor -%}
</ul>

<h3>Previous Meetings</h3>

<ul>
{%- assign sorted = site.github.public_repositories | sort: 'created_date' -%}
{%- for repository in sorted reversed -%}{%- if repository.has_pages -%}{%- unless repository.name contains 'github.io' -%}
  {% assign firstletter = repository.name | slice: 0, 2 %}
    {%-if firstletter=='e-' and repository.description contains '(previous)'-%}
    <li>
    <a href="{{ repository.name | prepend: site.baseurlsite }}"><b>{{ repository.description | replace: "(previous)" , "" }}</b></a>
    </li>
    {%-endif-%}
  {%- endunless -%}{%- endif -%}{%- endfor -%}
</ul>
