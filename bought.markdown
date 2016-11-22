---
layout: default
title: Wishlist (Bought)
---
<i>(Prices in curly brackets are in DKK by default.)</i>

* TOC
{:toc}

{% assign price_ranges = ">500" | split:"," %}
{% for range in price_ranges %}
### {{ range }},- ###
{% for w in site.data.wishes %}{% unless w.bought != true %}{% if w.price_range == range %}

<div class="tile" markdown="1">
#### {{ w.title }} {% if w.price %}<span style="white-space:nowrap">{**{{ w.price }},-**}</span>{% endif %} ####

{% if w.image %}![{{ w.title }}]({{ w.image }}){% endif %}

{% if w.link.dk or w.link.amazon %}
<span style="text-align: center;">{% if w.link.dk != false %}[[Dansk butik]({{ w.link.dk }})] / {% endif %}[[Amazon]({{ w.link.amazon }})]</span>
{% endif %}
{% if link.other %}<span style="text-align: center;">[[Purchase]({{ w.link.other }})]</span>{% endif %}
</div>
{% endif %}{% endunless %}{% endfor %}
{% endfor %}
