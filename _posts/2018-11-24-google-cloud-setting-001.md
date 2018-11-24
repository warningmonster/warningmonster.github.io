---
layout: post
title: "구글 클라우드 설치하기"
description: "구글 클라우드 설치하기"
modified: 2018-11-24
tags:  [구글 클라우드 설치하기, 구글 클라우드, 구글 클라우드 사용하기]
image:
  path: /images/abstract-5.jpg
  feature: abstract-5.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
---

# 구글 클라우드 설치하기

Creating a virtual machine instance
You can use these steps to deploy the LAMP stack using the Google Cloud Platform Console:

1. 클라우드 플랫폼 콘솔에서, VM 인스턴스 페이지로 이동
2. Click the Create instance button.
2. "Create instance" 버튼 클릭
3. lamp-tutorial에 이름 설정하기
4. Set Machine type to f1-micro.
4. "f1-micro" 타입으로 머신 설정
5. Boot disk 설정에서 "boot disk 환경으로 시작으로 변경" 선택
6. OS 이미지 탭에서, Debian 7.x, Ubuntu 14.04, CentOS 6.x, or CentOS 7.x version 선택.

<!-- more -->

Click Select.

In the Firewall section, select Allow HTTP traffic and Allow HTTPS traffic.
Click the Create button to create the instance.
Give the instance a few seconds to start up.


CentOS 6 and 7
Install Apache and PHP:

```
sudo yum check-update
sudo yum -y install httpd php
```

Start the Apache service:

sudo service httpd start
Optional: Set the Apache service to start automatically:

```
sudo chkconfig httpd on
```
