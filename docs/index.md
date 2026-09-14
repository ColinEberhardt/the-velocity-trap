---
layout: default
title: Contents
---
<div class="home">
  <h1 class="home-title">{{ site.title }}</h1>
  {% if site.subtitle %}<p class="home-subtitle">{{ site.subtitle }}</p>{% endif %}

  <img class="home-graphic" src="{{ '/assets/images/graphic.png' | relative_url }}" alt="">

  <div class="home-blurb">
    <p>{{ site.description }}</p>
  </div>

  {% if site.reading_time %}<p class="home-reading-time">{{ site.reading_time }}</p>{% endif %}

  {% assign chapters = site.chapters | sort: 'chapter_number' %}
  {% assign first_chapter = chapters | first %}
  <p class="home-cta">
    <a class="cta-link" href="{{ first_chapter.url | relative_url }}">Begin reading &rarr;</a>
  </p>

  <h2 class="toc-heading">Contents</h2>
  <ol class="toc-list">
    {% for chapter in chapters %}
    <li>
      {% if chapter.chapter_number == 0 %}
      <span class="toc-number">&mdash;</span>
      {% else %}
      <span class="toc-number">{{ chapter.chapter_number | prepend: "0" | slice: -2, 2 }}</span>
      {% endif %}
      <a href="{{ chapter.url | relative_url }}">{{ chapter.title }}</a>
    </li>
    {% endfor %}
  </ol>

  <nav class="chapter-nav" aria-label="Start reading">
    <span class="chapter-nav__spacer"></span>
    <span class="chapter-nav__spacer"></span>
    <a class="chapter-nav__next" href="{{ first_chapter.url | relative_url }}">Next &rarr;</a>
  </nav>
</div>
