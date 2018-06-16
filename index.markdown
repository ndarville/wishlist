---
layout: default
title: Wishlist
enable_charities: true
---
* TOC
{:toc}

{% if page.enable_charities == false %}
### Charities ###
{% for c in site.data.charities %}

<div class="tile" markdown="1">
#### {{ c.title | smartify }} ####

{% if c.image %}![Image for {{ c.title | smartify }}]({{ c.image }}){% endif %}

<span>[[Donate]({{ c.link }})]</span>
</div>
{% endfor %}
{% endif %}

{% for range in site.data.wishes %}
### {{ range[0] | replace:"lt","<" | replace:"gt",">" }} ###

{% for w in range[1] %}{% unless w.bought or w.hidden %}

<div class="tile" markdown="1">
#### {{ w.title | smartify }} {% if w.price %}<span style="white-space:nowrap">{**{{ w.price }}**}</span>{% endif %} ####

{% if w.image %}![Image for {{ w.title | smartify }}]({{ w.image }}){% endif %}

{% if w.link %}
<span>{% for l in w.link %}[[{{ l[0] | replace:"_"," " | capitalize }}]({{ l[1] }})]{% if forloop.length > 1 and forloop.last == false %} / {% endif %}{% endfor %}</span>
{% endif %}
</div>
{% endunless %}{% endfor %}
{% endfor %}
