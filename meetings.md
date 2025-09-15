---
title: Meetings
permalink: /meetings/
---

<br>
### <span style="color:#0095a9">Fintech Seminar Series</span>
<br>
<div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains 'meeting' %}
    <div class="list-item">
    <p class="list-post-title">
        <small>{{post.date | date: "%d/%m/%Y" }} {{ post.time }} Room: {{ post.location }}</small>: <b><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></b>
        {{post.content}}
        </p>
    </div>
    <hr>
    {% endif %}
  {% endfor %}
</div>


#### Other relevant meetings:


<hr>
{% include footer.html %}
