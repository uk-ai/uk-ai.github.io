---
layout: page
title: Home
---

The UK AI community connects AI researchers from across the country. We organise meetings where UK AI researchers gather to share their ideas.

<link rel="stylesheet" href="{{ '/assets/css/events-grid.css' | relative_url }}">

<h2 class="event-grid__heading">Meetings</h2>

<ul class="event-grid">
{%- assign events = site.data.events | sort: 'date' | reverse -%}
{%- assign today = site.time | date: "%Y-%m-%d" -%}
{%- for event in events -%}
  {%- assign event_day = event.date | date: "%Y-%m-%d" -%}
  <li>
    <a class="event-card{% unless event.image %} event-card--logo{% endunless %}" href="{{ event.url | relative_url }}"{% if event.image %} style="background-image: url('{{ event.image | relative_url }}')"{% endif %}>
      {%- if event_day >= today -%}
        <span class="event-card__badge">Upcoming</span>
      {%- endif -%}
      <span class="event-card__name">{{ event.name }}</span>
    </a>
  </li>
{%- endfor -%}
</ul>
