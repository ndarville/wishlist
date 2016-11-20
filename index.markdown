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

<div class="tile" markdown="1">
#### American Civil Liberties Union ####

<span style="text-align: center;">[[Donate](https://www.aclu.org)]</span>
</div>

{% assign data = site.data.wishes %}
{% assign price_ranges = "<250,>250,>500,>1000" | split:"," %}

{% for range in price_ranges %}
### {{ range }} ###
{% for w in data %}{% if w.price_range == range %}

<div class="tile" markdown="1">
#### {{ w.title }} {% if w.price %}(**{{ w.price }}**){% endif %} ####

{% if w.image %}![{{ w.title }}]({{ w.image }}){% endif %}

{% if w.link.dk or w.link.amazon %}
<span style="text-align: center;">{% if w.link.dk != false %}[[Dansk butik]({{ w.link.dk }})] / {% endif %}[[Amazon]({{ w.link.amazon }})]</span>
{% endif %}
</div>
{% endif %}{% endfor %}
{% endfor %}


[mini]: http://www.chromeindustries.com/product/mini-metro-messenger-bag/BG-001.html
[regular]: http://www.chromeindustries.com/product/citizen-messenger-bag/BG-002.html?dwvar_BG-002_color=BKBK&cgid=messenger_bags
