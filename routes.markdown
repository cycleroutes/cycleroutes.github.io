---
layout: page
permalink: /routes/
title: Routes
---


<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>

    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
      {% for post in site.categories[category_name] %}
      <article class="archive-item">
        <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
        <p>{{post.description}}</p>
        <p><b>Distance:</b> {{post.distance}}</p>
        <p><b>Elevation: </b>{{post.elevation}}</p>
        <p><b>Difficulty: </b>{{post.difficulty}}</p>
      </article>
      {% endfor %}
  </div>
{% endfor %}
</div>