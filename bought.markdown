---
layout: default
title: Wishlist (Bought)
---
{% for range in site.data.wishes %}
### {{ range[0] | replace:"lt","<" | replace:"gt",">" }} ###

{% for w in range[1] %}{% unless w.bought != true %}

<div class="tile" markdown="1">
#### {{ w.title | smartify }} {% if w.price %}<span style="white-space:nowrap">{**{{ w.price }}**}</span>{% endif %} ####

{% if w.image %}![Image for {{ w.title | smartify }}]({{ w.image }}){% endif %}

{% if w.link %}
<span>{% for l in w.link %}[[{{ l[0] | replace:"_"," " | capitalize }}]({{ l[1] }})]{% if forloop.length > 1 and forloop.last == false %} / {% endif %}{% endfor %}</span>
{% endif %}
</div>
{% endunless %}{% endfor %}
{% endfor %}
