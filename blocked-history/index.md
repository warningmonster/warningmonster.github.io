---
layout: page
title: 사이트 차단 이력
image:
  feature: abstract-3.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
comments: false
modified: 2018-10-28
---
<ul>
<h3> 통신사, 도메인, 최초 차단일, 마지막 차단일</h3>
{% for data in site.data.blocked-history %}
  <li>
    {{ data.telecom }} {{ data.domain }} {{ data.first_ymd }} {{ data.last_ymd }}
  </li>
{% endfor %}
</ul>
