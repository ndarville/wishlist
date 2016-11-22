---
layout: default
title: Wishlist
---
<i>(Prices in curly brackets are in DKK by default.)</i>

* TOC
{:toc}

* ["Parliament" book](http://www.parliamentbook.com/book)

<!--
    * Citizen Messenger bag (red)
        - `[x]` [Mini][] ($120)
        - `[ ]` [Regular][]
-->

### Charities ###
{% for c in site.data.charities %}

<div class="tile" markdown="1">
#### {{ c.title }} ####

<span style="text-align: center;">[[Donate]({{ c.link }})]</span>
</div>
{% endfor %}

{% assign price_ranges = "<250,>250,>500,>1000" | split:"," %}
{% for range in price_ranges %}
### {{ range }},- ###
{% for w in site.data.wishes %}{% unless price.bought %}{% if w.price_range == range %}

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


[mini]: http://www.chromeindustries.com/product/mini-metro-messenger-bag/BG-001.html
[regular]: http://www.chromeindustries.com/product/citizen-messenger-bag/BG-002.html?dwvar_BG-002_color=BKBK&cgid=messenger_bags
