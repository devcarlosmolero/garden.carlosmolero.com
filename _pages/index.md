---
layout: page
title: Home
id: home
permalink: /
---

# 🌱 Welcome!
This site is a compilation of all the thoughts, reflections, opinions and events that I feel like sharing with the world.

<p style="padding: 1em 1em; background: #f5f7ff; font-size: 0.88em; border-radius: 4px;">
I hope my content helps, inspires and pleases you, let's work to return the web to its original purpose: <b>to share knowledge and genuine experiences between people</b>.
</p>
- [[About me]]
- [[Hire me]]


<strong>Recently updated notes</strong>

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 5 %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>
    </li>
  {% endfor %}
</ul>

<style>
  .wrapper {
    max-width: 46em;
  }
</style>
