---
layout: page
title: 사이트 중단 이력
image:
  feature: abstract-5.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
comments: false
modified: 2018-10-28
---
<ul>
{% for data in site.data.shutdown-history %}
  <li>
    {{ data.date }} {{ data.event }}
  </li>
{% endfor %}
</ul>
