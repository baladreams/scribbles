---
layout: home
title: Scribbles
---

# Latest Stories

<ul>
  {% comment %} First, sort everything alphabetically by title {% endcomment %}
  {% assign alpha_stories = site.html_pages | sort: "title" %}
  
  {% comment %} Then, sort that alphabetical list by your optional order {% endcomment %}
  {% assign final_stories = alpha_stories | sort: "order" %}

  {% for story in final_stories %}
    {% if story.title and story.url != "/index.html" %}
      <li>
        <a href="{{ story.url | relative_url }}">{{ story.title }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>