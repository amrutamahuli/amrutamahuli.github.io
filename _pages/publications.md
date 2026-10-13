---
layout: page
permalink: /publications/
title: publications & talks
nav: true
nav_order: 2
---
{% include site-colors.html %}
<style>
.publications h2 {
  font-family: Georgia, serif;
  font-size: 1.2rem;
  color: #2E3A28;
  margin: 1.5rem 0 0.9rem;
  border-bottom: 1px solid #E3DED0;
  padding-bottom: 0.4rem;
}
.publications ol.bibliography {
  list-style: none;
  padding: 0;
  margin: 0;
}
.publications ol.bibliography li {
  background: #FFFFFF;
  border: 1px solid #E3DED0;
  border-radius: 8px;
  padding: 14px 16px;
  margin-bottom: 10px;
}
.publications ol.bibliography li .title {
  font-size: 13px;
  font-weight: 600;
  color: #2E3A28;
}
.publications ol.bibliography li .author {
  font-size: 11.5px;
  color: #6B7560;
}
.publications ol.bibliography li .periodical {
  font-size: 11.5px;
  color: #6B7560;
  font-style: italic;
}
  
.contrib-section-title {
  font-family: Georgia, serif;
  font-size: 1.2rem;
  color: #2E3A28;
  margin: 1.5rem 0 0.9rem;
  border-bottom: 1px solid #E3DED0;
  padding-bottom: 0.4rem;
}
.contrib-card {
  background: #FFFFFF;
  border: 1px solid #E3DED0;
  border-radius: 8px;
  padding: 10px 14px;
  margin-bottom: 8px;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 12px;
}
.contrib-title {
  font-size: 13px;
  font-weight: 600;
  margin: 0 0 2px;
  color: #2E3A28;
}
.contrib-venue {
  font-size: 11.5px;
  color: #6B7560;
  margin: 0;
}
.contrib-tag {
  font-size: 10px;
  padding: 3px 8px;
  border-radius: 20px;
  white-space: nowrap;
}
.tag-talk { background: #E6F1FB; color: #0C447C; }
.tag-policy { background: #FAECE7; color: #712B13; }
.tag-writing { background: #EEEDFE; color: #3C3489; }
</style>

<p class="contrib-section-title">Academic Publications</p>
<div class="publications">
{% bibliography %}
</div>

<p class="contrib-section-title">Talks &amp; Panels</p>
{% assign sorted_talks = site.data.contributions.talks | sort: 'year' | reverse %}
{% for item in sorted_talks %}
<div class="contrib-card">
  <div>
    <p class="contrib-title">{{ item.title }}</p>
    <p class="contrib-venue">{{ item.venue }}</p>
  </div>
  <span class="contrib-tag tag-talk">{{ item.type }} &middot; {{ item.year }}</span>
</div>
{% endfor %}

<p class="contrib-section-title">Policy Contributions</p>
{% assign sorted_policy = site.data.contributions.policy | sort: 'year' | reverse %}
{% for item in sorted_policy %}
<div class="contrib-card">
  <div>
    <p class="contrib-title">{{ item.title }}</p>
    <p class="contrib-venue">{{ item.venue }}</p>
  </div>
  <span class="contrib-tag tag-policy">{{ item.type }} &middot; {{ item.year }}</span>
</div>
{% endfor %}

<p class="contrib-section-title">Writing</p>
{% assign sorted_writing = site.data.contributions.writing | sort: 'year' | reverse %}
{% for item in sorted_writing %}
<div class="contrib-card">
  <div>
    <p class="contrib-title"><a href="{{ item.url }}" target="_blank" rel="noopener">{{ item.title }}</a></p>
    <p class="contrib-venue">{{ item.venue }}</p>
  </div>
  <span class="contrib-tag tag-writing">{{ item.type }} &middot; {{ item.year }}</span>
</div>
{% endfor %}
