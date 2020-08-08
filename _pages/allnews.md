---
title: "News"
layout: textlay
excerpt: "Computational Materials and Chemical Processes Laboratory"
sitemap: false
permalink: /allnews.html
---

# News

{% for article in site.data.news %}
<p>{{ article.date }} <br>
{{ article.headline }}</p>
{% endfor %}
