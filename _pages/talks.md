---
layout: page
permalink: /talks/
title: Talks
description: A list of selected talks and presentations
nav: true
nav_order: 6
---
{% assign talks_sorted = site.talks | sort: 'date' %}
{% for talk in talks_sorted reversed %}
<div class="talk-item">
  <h3><a href="{{ talk.url | relative_url }}">{{ talk.title | escape }}</a></h3>
  <p class="talk-meta">{{ talk.date | date: "%Y-%m-%d" }} — {{ talk.location }}</p>
  {% if talk.excerpt %}
    <div class="talk-excerpt">{{ talk.excerpt }}</div>
  {% endif %}

  {% if talk.link or talk.slides or talk.video %}
    <p class="talk-links">
      {% if talk.link %}
        <a class="talk-link" href="{{ talk.link }}" target="_blank" rel="noopener noreferrer">Event</a>
      {% endif %}
      {% if talk.slides %}
        {% if talk.link %} &nbsp;|&nbsp; {% endif %}
        <a class="talk-link" href="{{ talk.slides }}" target="_blank" rel="noopener noreferrer">Slides</a>
      {% endif %}
      {% if talk.video %}
        {% if talk.link or talk.slides %} &nbsp;|&nbsp; {% endif %}
        <a class="talk-link" href="{{ talk.video }}" target="_blank" rel="noopener noreferrer">Video</a>
      {% endif %}
    </p>
  {% endif %}
</div>
{% endfor %}

