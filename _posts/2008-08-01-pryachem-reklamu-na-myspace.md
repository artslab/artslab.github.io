---
id: 363
title: Прячем рекламу на myspace
date: 2008-08-01T01:41:54+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=363
permalink: /sovetyi/pryachem-reklamu-na-myspace/
ljID:
  - 213
prosmotr:
  - 68
wpb_post_views_count:
  - 919
dsq_thread_id:
  - 1565022393
cover:
  - 
categories:
  - Советы
tags:
  - myspace
  - Хаки
---
<p style="text-align: center;">
  <img class="aligncenter" style="border: 0pt none;" src="http://clip2net.com/clip/m6048/1217543209-clip-4kb.jpg" alt="myspace без рекламы" width="188" height="49" />
</p>

Я думаю у многих пользователей рунета есть свои аккаунт в известной зарубежной соц. сети <a href="http://myspace.com/" target="_blank">myspace</a> и наверняка, некоторым хотелось бы убрать рекламный баннер со странички своего профиля. Сегодня я помогал одному другу с оформлением профиля на myspace и столкнулся с этим, решение нашлось довольно таки быстро, спасибо конечно же нашему любимому google 🙂

Итак, все что нужно сделать, это зайти в редактирование профиля -> About me (_куда можно добавлять html и css_) и вписать туда несколько строчек:

[css]
  
.clearfix {
  
display:none !important;
  
position:absolute!important;
  
}
  
[/css]

Источник: <a href="http://jericosystems.com/2008/07/02/hide-ads-on-myspace/" target="_blank">Jerico Systems</a>

_PS: Конечно же все это на свой страх и риск, так как, насколько мне известно это противоречит правилам сайта&#8230;_