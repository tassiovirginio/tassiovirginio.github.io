---
layout: default
title: Sínteses
permalink: /sinteses/
robots: noindex
---

#### **Aqui se encontra a síntese de alguns artigos que achei interessante:**
<br>

<div class="main-post-list">

  <ol class="post-list">
    {% for post in site.posts %}
      {% if post.categories contains 'sintese' %}
      <li>
        <h2 class="post-list__post-title post-title"><a href="{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h2>
        <p class="excerpt">{{ post.excerpt | strip_html }}&hellip;</p>
        <div class="post-list__meta">
            <time datetime="{{ post.date | date: "%Y-%m-%d %H:%M" }}" class="post-list__meta--date date">{{ post.date | date: "%-d %b %Y" }}</time>
            {% if post.tags.size > 0 %}
            &#8226; <span class="post-meta__tags">on {% for tag in post.tags %}<a href="{{ site.baseurl }}/tags/#{{ tag }}">{{ tag }}</a> {% endfor %}</span>
            {% endif %}
        </div>
        <hr class="post-list__divider">
      </li>
      {% endif %}
    {% endfor %}
  </ol>

  <hr class="post-list__divider ">

  {% if paginator.previous_page or paginator.next_page %}
      {% include pagination.html %}
  {% endif %}

</div>