---
layout: default
title: Wishlist (Bought)
price_ranges:
#   - "<250"
    - ">250"
    - ">500"
    - ">1000"
---
<i>(Prices in curly brackets are in DKK by default.)</i>

* TOC
{:toc}

{% for range in page.price_ranges %}
### {{ range }},- ###
{% for w in site.data.wishes %}{% unless w.bought != true %}{% if w.price_range == range %}

<div class="tile" markdown="1">
#### {{ w.title }} {% if w.price %}<span style="white-space:nowrap">{**{{ w.price }},-**}</span>{% endif %} ####

{% if w.image %}![{{ w.title }}]({{ w.image }}){% endif %}

{% if w.link.dk or w.link.bookdepository or w.link.amazon %}
<span style="text-align: center;">{% if w.link.dk %}[[Dansk butik]({{ w.link.dk }})]{% if w.link.amazon %} / {% endif %}{% endif %}{% if w.link.bookdepository %}[[Book Depository]({{ w.link.bookdepository }})]{% if w.link.amazon %} / {% endif %}{% endif %}{% if w.link.amazon %}[[Amazon]({{ w.link.amazon }})]{% endif %}</span>
{% else %}
<span style="text-align: center;">[[Purchase]({{ w.link.other }})]</span>
{% endif %}
</div>
{% endif %}{% endunless %}{% endfor %}
{% endfor %}
