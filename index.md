---
layout: page
title: Home
---

The UK AI community connects AI researchers from across the country. We organise meetings where UK AI researchers gather to share their ideas.

<h3>Upcoming Meetings</h3>

<ul>
{%- assign sorted = site.github.public_repositories | sort: 'created_at' -%}
{%- for repository in sorted reversed -%}
  {%- if repository.has_pages -%}
    {%- unless repository.name contains 'github.io' -%}
      {%- if repository.description contains '(upcoming-event)' -%}
        <li>
          <a href="{{ repository.name | prepend: site.baseurlsite }}" target="_blank"><b>{{ repository.description | replace: "(upcoming-event)", "" }}</b></a>
        </li>
      {%- endif -%}
    {%- endunless -%}
  {%- endif -%}
{%- endfor -%}
</ul>

<h3>Previous Meetings</h3>

<ul>
{%- assign sorted = site.github.public_repositories | sort: 'created_at' -%}
{%- for repository in sorted reversed -%}
  {%- if repository.has_pages -%}
    {%- unless repository.name contains 'github.io' -%}
      {%- if repository.description contains '(previous-event)' -%}
        <li>
          <a href="{{ repository.name | prepend: site.baseurlsite }}" target="_blank"><b>{{ repository.description | replace: "(previous-event)" , "" }}</b></a>
        </li>
      {%- endif -%}
    {%- endunless -%}
  {%- endif -%}
{%- endfor -%}
</ul>
