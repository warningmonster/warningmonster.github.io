---
layout: post
title: "서브라임 텍스트 설치하기"
description: "서브라임 텍스트 설치하기"
modified: 2018-12-13
tags:  [서브라임, 써브라임, 서브라임 텍스트, sublime, sublime text, 서브라임 텍스트 설치하기]
image:
  path: /images/abstract-6.jpg
  feature: abstract-6.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
---
1. 다운로드 URL = https://www.sublimetext.com/3
2. sublime text3 설치
3. Package control 설치
   https://sublime.wbond.net/installation#st3
   여기에 가서 아래 문장 복사
   . 단축키 : ctrl+`
   . 메뉴에서 찾아가기 : View > Show Console menu   
   ~~~
   import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
   ~~~
   . 서브라임 텍스트 프로그램을 껐다 키기  
   . Tools->Command Pallet 또는 (Ctrl-Shift-P) 를 클릭  
   . Install Package 선택  
   


<!-- more -->
. 
