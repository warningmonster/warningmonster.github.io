---
layout: page
title: 사이트 차단 이력
image:
  feature: abstract-3.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
table_design_active: true     # table design을 적용하라는 의미
comments: false
modified: 2018-10-28
---
<table id="dalt-table-17" class="dalt-table">
<thead>
  <tr>
    <th>통신사</th>
    <th>도메인</th>
    <th>최초차단일</th>
    <th>최근차단일</th>
  </tr>
</thead>
<tbody>
{% for data in site.data.blocked-history %}
  <tr>
    <td>{{ data.telecom }}</td><td>{{ data.domain }}</td><td>{{ data.first_ymd }}</td><td>{{ data.last_ymd }}</td>
  </tr>
{% endfor %}
</tbody>
</table>
