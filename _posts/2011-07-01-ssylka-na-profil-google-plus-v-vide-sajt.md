---
id: 3510
title: 'Ссылка на профиль Google Plus в виде &#8211; сайт/+'
date: 2011-07-01T13:56:44+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=3510
permalink: /socialnye-seti/ssylka-na-profil-google-plus-v-vide-sajt/
ljID:
  - 428
sbg_selected_sidebar:
  - 'a:5:{i:0;s:1:"0";i:1;s:1:"0";i:2;s:1:"0";i:3;s:1:"0";i:4;s:1:"0";}'
sbg_selected_sidebar_replacement:
  - 'a:5:{i:0;s:1:"0";i:1;s:1:"0";i:2;s:1:"0";i:3;s:1:"0";i:4;s:1:"0";}'
onswipe_thumb:
  - {{site.img_cdn}}/google_plus_logo.jpg
prosmotr:
  - 123
wpb_post_views_count:
  - 1698
dsq_thread_id:
  - 1565018924
categories:
  - socialnye-seti
tags:
  - google plus
---
<center>
  <a href="{{site.img_cdn}}/google_plus_logo.jpg"><img src="{{site.img_cdn}}/google_plus_logo.jpg" alt="Логотип Google Plus" title="google_plus_logo" width="140" height="54" class="alignnone size-full wp-image-3513" /></a>
</center>

Продолжение гуглотемы. Наткнулся на одну интересную задумку, а почему бы не поставить ссылку на свой профиль Google + в таком виде: http://sitename.ru/+ .

По-моему довольно-таки оригинально и реализуется очень просто.

Необходимо открыть файл .htaccess и добавить в него одну строку:

[sourcecode language=&#8221;html&#8221;]Redirect 301 /+ https://plus.google.com/ваш_id/[/sourcecode]

Если что, я здесь <http://artslab.info/+>.

_[Источник](http://www.eisy.eu/trend-google-plus-profile-als-verlinken/) (Danke f&uuml;r die Idee =) )_