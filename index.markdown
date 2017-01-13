---
layout: default
title: Wishlist
---
<i>(Prices in curly brackets are in DKK by default.)</i>

* TOC
{:toc}

### Charities ###
{% for c in site.data.charities %}

<div class="tile" markdown="1">
#### {{ c.title | smartify }} ####

<span>[[Donate]({{ c.link }})]</span>
</div>
{% endfor %}

{% for range in site.data.wishes %}
### {{ range[0] | replace:"lt","<" | replace:"gt",">" }},- ###

{% for w in range[1] %}{% unless w.bought or w.hidden %}

<div class="tile" markdown="1">
#### {{ w.title | smartify }} {% if w.price %}<span style="white-space:nowrap">{**{{ w.price }},-**}</span>{% endif %} ####

{% if w.image %}![{{ w.title | smartify }}]({{ w.image }}){% endif %}

{% if w.link.dk or w.link.bookdepository or w.link.amazon %}
<span>{% if w.link.dk %}[[Dansk butik]({{ w.link.dk }})]{% if w.link.amazon %} / {% endif %}{% endif %}{% if w.link.bookdepository %}[[Book Depository]({{ w.link.bookdepository }})]{% if w.link.amazon %} / {% endif %}{% endif %}{% if w.link.amazon %}[[Amazon]({{ w.link.amazon }})]{% endif %}</span>
{% endif %}
{% if w.link.other %}
<span>[[Purchase]({{ w.link.other }})]</span>
{% endif %}
</div>
{% endunless %}{% endfor %}
{% endfor %}
