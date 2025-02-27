---
title: News
permalink: /news/
---

<br>
### **Latest News**
<br>
<div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains 'news' %}
    <div class="list-item">
    <p class="list-post-title">
        <small>{{post.date | date: "%d/%m/%Y" }}</small>: <b><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></b>
        {{post.content}}
        </p>
    </div>
    <hr>
    {% endif %}
  {% endfor %}
</div>


<br>
<hr>
{% include footer.html %}
