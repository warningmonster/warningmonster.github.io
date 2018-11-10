---
layout: page
title: 사이트 차단 이력
image:
  feature: abstract-3.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
table_design_active: true     # table design을 적용라는 의미
comments: false
modified: 2018-10-28
---
<table id="dalt-table-17" class="dalt-table" data-enable-sorting="0" data-enable-manual-sorting="0" data-show-position="1" data-position-side="left" data-position-label="#" data-number-format="0" data-order-desc-asc-1="0" data-order-by-1="1"
  data-order-data-type-1="auto" data-order-date-format-1="ddmmyyyy" data-order-desc-asc-2="0" data-order-by-2="1" data-order-data-type-2="auto" data-order-date-format-2="ddmmyyyy" data-order-desc-asc-3="0" data-order-by-3="1" data-order-data-type-3="auto"
  data-order-date-format-3="ddmmyyyy" data-order-desc-asc-4="0" data-order-by-4="1" data-order-data-type-4="auto" data-order-date-format-4="ddmmyyyy" data-order-desc-asc-5="0" data-order-by-5="1" data-order-data-type-5="auto"
  data-order-date-format-5="ddmmyyyy" data-table-width="0" data-table-width-value="400" data-table-minimum-width="0" data-table-margin-top="20" data-table-margin-bottom="20" data-enable-container="0" data-container-width="400" data-container-height="400"
  data-header-font-size="11" data-header-font-family="'Open Sans', Helvetica, Arial, sans-serif" data-header-font-weight="400" data-header-font-style="normal" data-header-background-color="#C3512F" data-header-font-color="#FFFFFF"
  data-header-link-color="#FFFFFF" data-header-border-color="#B34A2A" data-header-position-alignment="center" data-body-font-size="11" data-body-font-family="'Open Sans', Helvetica, Arial, sans-serif" data-body-font-weight="400" data-body-font-style="normal"
  data-even-rows-background-color="#FFFFFF" data-odd-rows-background-color="#FCFCFC" data-even-rows-font-color="#666666" data-even-rows-link-color="#C3512F" data-odd-rows-font-color="#666666" data-odd-rows-link-color="#C3512F" data-rows-border-color="#E1E1E1"
  data-autocolors-priority="rows" data-autocolors-affected-rows-1="" data-autocolors-rows-background-color-1="#FFFFFF" data-autocolors-rows-font-color-1="#666666" data-autocolors-affected-rows-2="" data-autocolors-rows-background-color-2="#FFFFFF"
  data-autocolors-rows-font-color-2="#666666" data-autocolors-affected-rows-3="" data-autocolors-rows-background-color-3="#FFFFFF" data-autocolors-rows-font-color-3="#666666" data-autocolors-affected-rows-4="" data-autocolors-rows-background-color-4="#FFFFFF"
  data-autocolors-rows-font-color-4="#666666" data-autocolors-affected-rows-5="" data-autocolors-rows-background-color-5="#FFFFFF" data-autocolors-rows-font-color-5="#666666" data-autocolors-affected-columns-1=""
  data-autocolors-columns-background-color-1="#FFFFFF" data-autocolors-columns-font-color-1="#666666" data-autocolors-affected-columns-2="" data-autocolors-columns-background-color-2="#FFFFFF" data-autocolors-columns-font-color-2="#666666"
  data-autocolors-affected-columns-3="" data-autocolors-columns-background-color-3="#FFFFFF" data-autocolors-columns-font-color-3="#666666" data-autocolors-affected-columns-4="" data-autocolors-columns-background-color-4="#FFFFFF"
  data-autocolors-columns-font-color-4="#666666" data-autocolors-affected-columns-5="" data-autocolors-columns-background-color-5="#FFFFFF" data-autocolors-columns-font-color-5="#666666" data-autoalignment-priority="rows"
  data-autoalignment-affected-rows-left="" data-autoalignment-affected-rows-center="" data-autoalignment-affected-rows-right="" data-autoalignment-affected-columns-left="" data-autoalignment-affected-columns-center=""
  data-autoalignment-affected-columns-right="" data-tablet-breakpoint="989" data-hide-tablet-list="" data-tablet-header-font-size="11" data-tablet-body-font-size="11" data-tablet-hide-images="0" data-phone-breakpoint="479" data-hide-phone-list=""
  data-phone-header-font-size="11" data-phone-body-font-size="11" data-phone-hide-images="0" data-enable-cell-properties="1">
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
