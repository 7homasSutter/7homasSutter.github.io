---
layout: page
permalink: /teaching/
title: Teaching
description: "Courses I teach or assist with"
nav: true
nav_order: 5
---

{%- assign courses_sorted = site.courses | where_exp: "c", "c.published != false" | sort: 'year' | reverse -%}

{%- for course in courses_sorted -%}

  <div class="course-item">
	<h3 class="course-title"><a href="{{ course.url | relative_url }}">{{ course.title }}</a></h3>
	<p class="course-subtitle">
	  {% if course.year %}{{ course.year }}{% elsif course.term %}{{ course.term }}{% endif %}
	  {% if course.level %} &middot; {{ course.level }}{% endif %}
	  {% if course.university %}
		&middot; <a class="course-university" href="{{ course.university_url | default: course.university_link | default: '#' }}">{{ course.university }}</a>
	  {% endif %}
	</p>

    {% if course.excerpt %}
      <p class="course-desc">{{ course.excerpt }}</p>
    {% elsif course.description %}
      <p class="course-desc">{{ course.description }}</p>
    {% endif %}

  </div>
{%- endfor -%}
