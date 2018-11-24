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
##### - Cloud : Google Cloud [https://cloud.google.com]  
##### - OS : CentOS 7.x  
##### - 설치 SW  
  1. Apache  
  2. PHP  
  3. mongodb  

##### - 설정하기  
  1. SSH
  2. github or gitlab

<!-- more -->

##### 1. Apache, PHP 설치  
###### . 설치
```
sudo yum check-update
sudo yum -y install httpd php
```

###### . 웹서버 가동
```
sudo service httpd start
```

###### . (안해도 무방) OS 기동되면 아파치가 자동으로 실행되게 설정하기
```
sudo chkconfig httpd on
```

###### . PHP 테스트 페이지 만들기
```
sudo sh -c 'echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php'
```

###### . 사이트 접속해보기
```
http://[YOUR_EXTERNAL_IP_ADDRESS]/phpinfo.php
```

##### 2. mongodb 설치
```
sudo chkconfig httpd on
```

##### 3. ssh 설정


##### 4. 참고문헌
. https://cloud.google.com/community/tutorials/setting-up-lamp
