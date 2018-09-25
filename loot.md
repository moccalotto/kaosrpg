---
layout: post
---

This tome contains examples of cool loot the players can find.

OWNING MAGICAL ITEMS
====================

Owning a magical item is a special thing.
When you own a magical item, you can use it and you gain the benefits of
owning it.

To truly own an item, you must 

* Honestly believe that the item is yours.
* Have spent at least two hours studying the item.
* Have had the item in your possession for the last two days.


You can only truly »own« 3 magical items. You can carry more than
that of course, but actually owning the item is a different matter.


LIST OF LOOT
============

{% assign items = site.loot | sort: "title" %}

{% for item in items %}

### {{ item.title }}

{{ item.content | markdownify }}

{% endfor %}
