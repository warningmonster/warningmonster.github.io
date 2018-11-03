---
layout: page
title: History
image:
  feature: abstract-5.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
comments: false
modified: 2018-10-28
---
{% for event in site.data.history %}
  {{ event.date }}, {{ event.title }} <br>
{% endfor %}
