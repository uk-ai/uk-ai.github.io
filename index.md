---
layout: page
title: Home
---

The UK AI community is a hub where researchers and practitioners from across the country meet, share ideas, and build academic relationships. We organise accessible events focused on early-career researchers to build and promote technical AI, and to work together on its safety, responsibility, and trustworthiness.

<link rel="stylesheet" href="{{ '/assets/css/events-grid.css' | relative_url }}?v=20261019">

<h2 class="event-grid__heading">Meetings</h2>

<ul class="event-grid">
{%- assign events = site.data.events | sort: 'date' | reverse -%}
{%- assign today = site.time | date: "%Y-%m-%d" -%}
{%- for event in events -%}
  {%- assign event_day = event.date | date: "%Y-%m-%d" -%}
  <li>
    <a class="event-card{% unless event.image %} event-card--logo{% endunless %}{% if event.credit %} event-card--credit{% endif %}" href="{{ event.url | relative_url }}"{% if event.image %} style="background-image: url('{{ event.image | relative_url }}')"{% endif %}>
      {%- if event_day >= today -%}
        <span class="event-card__badge">Upcoming</span>
      {%- endif -%}
      <span class="event-card__name">{{ event.name }}</span>
      {%- if event.credit -%}
        <span class="event-card__credit">{{ event.credit }}</span>
      {%- endif -%}
    </a>
  </li>
{%- endfor -%}
</ul>
