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
#### {{ c.title }} ####

<span style="text-align: center;">[[Donate]({{ c.link }})]</span>
</div>
{% endfor %}

{% for range in site.data.wishes %}
### {{ range[0] | replace:"lt","<" | replace:"gt",">" }},- ###

{% for w in range[1] %}{% unless w.bought or w.hidden %}

<div class="tile" markdown="1">
#### {{ w.title }} {% if w.price %}<span style="white-space:nowrap">{**{{ w.price }},-**}</span>{% endif %} ####

{% if w.image %}![{{ w.title }}]({{ w.image }}){% endif %}

{% if w.link.dk or w.link.bookdepository or w.link.amazon %}
<span style="text-align: center;">{% if w.link.dk %}[[Dansk butik]({{ w.link.dk }})]{% if w.link.amazon %} / {% endif %}{% endif %}{% if w.link.bookdepository %}[[Book Depository]({{ w.link.bookdepository }})]{% if w.link.amazon %} / {% endif %}{% endif %}{% if w.link.amazon %}[[Amazon]({{ w.link.amazon }})]{% endif %}</span>
{% endif %}
{% if w.link.other %}
<span style="text-align: center;">[[Purchase]({{ w.link.other }})]</span>
{% endif %}
</div>
{% endunless %}{% endfor %}
{% endfor %}


[mini]: http://www.chromeindustries.com/product/mini-metro-messenger-bag/BG-001.html
[regular]: http://www.chromeindustries.com/product/citizen-messenger-bag/BG-002.html?dwvar_BG-002_color=BKBK&cgid=messenger_bags
