---
title: "Computational Materials and Chemical Processes Lab - Publications"
layout: gridlay
excerpt: "Computational Materials and Chemical Processes Lab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

[Google Scholar](https://scholar.google.com/citations?hl=en&user=1bRl4o4AAAAJ)

{% assign yeartest = true %}
{% for publi in site.data.publist %}
  {% if publi.year %}{% else %}
   {% assign yeartest = false %}
  {% endif %}
{% endfor %}

{% if yeartest == false %}
## Coming Soon
{% endif %}

{% for publi in site.data.publist %}
  {% if publi.year %}{% else %}
  <div class="well-sm">
  <ul class="flex-container">
  <li class="flex-item">
  <strong> {{ publi.title }}</strong><br/>
  <i>{{ publi.authors }} </i><br/>
  {{ publi.display }}<br/>
  {% if publi.doi %}<a href="http://dx.doi.org/{{ publi.doi }}" target="blank"><button class="btn-doi">DOI</button></a> {% endif %}
  </li>
  </ul>
  </div>
  {% endif %}
{% endfor %}

{% if site.group_pub_by_year == true %}{% else %}
### Journal Papers and Proceedings
{% endif %}

{% for myyear in site.data.years %}

{% assign yeartest = false %}
{% for publi in site.data.publist %}
  {% if publi.year == myyear.year %}
   {% assign yeartest = true %}
  {% endif %}
{% endfor %}

{% if site.group_pub_by_year == true %}
{% if yeartest == true %}
## {{ myyear.year }}
{% endif %}
{% endif %}

{% for publi in site.data.publist %}
{% if publi.year == myyear.year %}

<div class="well-sm">
<ul class="flex-container">
<li class="flex-item">
  <b>{{ publi.title }}</b><br/>
  {{ publi.authors }}<br/>
  <b>{{ publi.journal }}</b>, {{ publi.journal_pagination }} ({{publi.year}}) <br/>
  {% if publi.doi %}<a href="http://dx.doi.org/{{ publi.doi }}" target="blank"><button class="btn-doi">DOI</button></a> {% endif %}
  {% if publi.fund %}<button class="btn-fund1">{{ publi.fund }}</button>{% endif %}
  {% if publi.comp %}<button class="btn-comp1">{{ publi.comp }}</button>{% endif %}

</li>
</ul>
</div>
{% endif %}
{% endfor %}

{% endfor %}
