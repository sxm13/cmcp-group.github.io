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
  {% if publi.nrf-2019 %}<button class="btn-nrf-2016">NRF-2016R1D1A1B03934484</button><% endif %>
  {% if publi.nrf-2020 %}<button class="btn-nrf-2020">NRF-2020R1C1C1010373</button><% endif %>
  {% if publi.ksc-2019 %}<button class="btn-ksc-2019">KSC-2019-CRE-0203</button><% endif %>
  {% if publi.ksc-2020 %}<button class="btn-ksc-2020">KSC-2020-CRE-0013</button><% endif %>
  <button class="btn-funding1">NRF-2020R1C1C1010373</button>

</li>
</ul>
</div>
{% endif %}
{% endfor %}

{% endfor %}
