---
layout: page
permalink: /service/
title: service & teaching
nav: true
nav_order: 4
---
{% include site-colors.html %}
<style>
.tag-service { background: #E6F1FB; color: #0C447C; }
.tag-teaching { background: #FAECE7; color: #712B13; }
</style>

<p class="contrib-section-title">Service</p>
{% assign sorted_service = site.data.contributions.service | sort: 'year' | reverse %}
{% for item in sorted_service %}
<div class="contrib-card">
  <div>
    <p class="contrib-title">{{ item.title }}</p>
    {% if item.venue != "" %}<p class="contrib-venue">{{ item.venue }}</p>{% endif %}
  </div>
  <span class="contrib-tag tag-service">{{ item.type }} &middot; {{ item.year }}</span>
</div>
{% endfor %}

<p class="contrib-section-title">Teaching</p>
{% assign sorted_teaching = site.data.contributions.teaching | sort: 'year' | reverse %}
{% for item in sorted_teaching %}
<div class="contrib-card">
  <div>
    <p class="contrib-title">{{ item.title }}</p>
    <p class="contrib-venue">{{ item.venue }}</p>
  </div>
  <span class="contrib-tag tag-teaching">{{ item.type }} &middot; {{ item.year }}</span>
</div>
{% endfor %}
