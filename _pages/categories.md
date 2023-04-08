---
layout: page
permalink: /categorias/
title: Categorías
---

<h1 class="entry-title">Artículos clasificados por categorias</h1>

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    
    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    <ul>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <li><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></li>
    </article>
    {% endfor %}
    </ul>
  </div>
{% endfor %}
</div>

<hr>
<h3>Artículos ordenador <a href="{{ site.baseurl }}/archivo">por año</a></h3>
{:style="text-align:center;"}