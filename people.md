---
title: People
permalink: /people/
---

<!-- set true/false if there is a newsflash announcement -->
{% if true %}
  {% include newsflash.html %}
{% else %}
  <br>  
{% endif %}
<!-- end of newsflash area -->

<h2>Financial Engineering Lab</h2>
FEL is a unit of [Intelligent Systems Laboratory (ISL)](https://www.bristol.ac.uk/research/groups/intelligent-systems/).
<br>
<p>Researchers in the Financial Engineering Lab (FEL) develop and apply methods from AI, Machine Learning (ML), Data Science, and advanced simulation/modelling techniques to explore and address issues in present-day and future financial systems. FEL research spans from the “micro” of creating reliably profitable adaptive automated trading systems that can operate autonomously in contemporary electronic financial markets; through intermediate-level issues such as the design of novel market mechanisms and institutions; to “macro” level issues such as modelling and predicting systemic risk and stability in entire national or international financial systems.
</p>

{% assign people_sorted = site.people | sort: "joined" %}
{% assign people_array = "pi|postdoc|gradstudent|visiting|others" | split: "|" %}

<!--
{% assign people_sorted = site.people | sort: "joined" %}
<ul>
{% for y in yearsSorted %}
  <li>{{ y.name }}
    <ul>
      {% assign yearTitlesSorted = y.items | sort: "title" %}
      {% for t in yearTitlesSorted %}
      <li>{{ t.title }}</li>
      {% endfor %}
    </ul>
  </li>
{% endfor %}
</ul>-->

{% for item in people_array %}

<div class="pos_header">
{% if item == 'postdoc' %}
<h3>Postdoctoral research associates</h3>
 {% elsif item == 'pi' %}
<h3>Core faculty</h3>
 {% elsif item == 'gradstudent' %}
<h3>Doctoral students</h3>
{% elsif item == 'visiting' %}
<h3>Visiting scholars</h3>
 {% elsif item == 'others' %} 
<h3>Affiliated faculty</h3>
{% elsif item == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people">
      <p class="list-post-title">
        {% if profile.website %}
          {% assign url_tmp = profile.website %}
        {% else %}
          {% assign url_tmp = site.baseurl | append: profile.url %}
        {% endif %}
        {% if profile.avatar %}
        <a href="{{url_tmp}}"><img width="200" height="230" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
        {% else %}
        <a href=""><img width="200" height="230" src="{{site.baseurl}}/images/people/facebook-Storm-Trooper.jpg"></a>
        {% endif %}
        <a class="name" href="{{url_tmp}}">{{ profile.name }}</a>
        {% if profile.affiliation %}
          <br><small><span style="color:#9d9d9d">{{ profile.affiliation }}</span></small>
        {% else %}
          <br><small><span style="color:#FFFFFF">.</span></small>
        {% endif %}
      </p>
    </div>
    {% endif %}
  {% endfor %}
</div>
<hr>
{% endfor %}

List of [Financial Engineering Lab (FEL) alumni](/people/alumni).

<hr>

{% include footer.html %}


