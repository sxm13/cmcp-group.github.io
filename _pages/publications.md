---
title: "Computational Materials and Chemical Processes Lab - Publications"
layout: gridlay
excerpt: "Computational Materials and Chemical Processes Lab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

[Google Scholar](https://scholar.google.ch/citations?user=TqxYWZsAAAAJ)

{% assign yeartest = true %}
{% for publi in site.data.publist %}
  {% if publi.year %}{% else %}
   {% assign yeartest = false %}
  {% endif %}
{% endfor %}

{% if yeartest == false %}
