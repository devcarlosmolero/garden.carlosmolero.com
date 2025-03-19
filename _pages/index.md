---
layout: page
title: Home
id: home
permalink: /
---

# 🌱 Welcome!

This is a space of all the thoughts, reflections, opinions and events that I feel like sharing with the world.

## Why a digital garden and not a blog?

I prefer to write short and concise ideas that I can revisit later to expand upon. For this reason, I felt that the traditional blog format didn't suit me.

I believe that blogs, especially now with AI, have become tools focused on monetization and marketing, straying from their original purpose: **sharing human knowledge and experiences**.

<div class="notice">
I hope my content helps, inspires and pleases you, let's work to return the web to its original purpose: <b>to share knowledge and genuine experiences between people</b>.
</div>

<strong>Let's meet each other</strong>

- [[About me]]
- [[Hire me]]

<strong>Don't know where to start? Try these lists</strong>

<ul>
  {% assign notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in notes %}
    {% if note['list'] == "true" %}
      <li>
        {{ note.last_modified_at | date: "%Y-%m-%d" }} — {{ note.emoji }} <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>

<strong>Recently updated notes</strong>

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 10 %}
      {% if note['list'] != "true" %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>
    </li>
        {% endif %}
  {% endfor %}
</ul>

<style>
  .wrapper {
    max-width: 46em;
  }
</style>
