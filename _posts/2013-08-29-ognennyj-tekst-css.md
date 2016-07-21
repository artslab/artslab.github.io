---
id: 7643
title: Огненный текст (CSS)
date: 2013-08-29T12:21:57+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7643
permalink: /snippety/ognennyj-tekst-css/
cover:
  - 
wpb_post_views_count:
  - 1133
dsq_thread_id:
  - 1664463792
ratings_users:
  - 1
ratings_score:
  - 4
ratings_average:
  - 4
categories:
  - Сниппеты
tags:
  - css
  - сниппет
---
Продолжим экспериментировать с различными текстовыми эффектами и создадим &#8220;огненный&#8221; текст используя возможности CSS.

<center>
  <a href="http://img.artslab.info/ognenii_tekst.png"><img src="http://img.artslab.info/ognenii_tekst-300x173.png" alt="огненный текст" class="aligncenter size-medium wp-image-7644" srcset="http://img.artslab.info/ognenii_tekst-300x173.png 300w, http://img.artslab.info/ognenii_tekst.png 780w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>


  
<!--more-->

Код класса:

[css]
  
.fire-text {
      
text-align: center;
      
margin: 200px auto;
      
font-size: 120px;
      
color: #fff;
      
text-shadow: 0 0 20px #fefcc9, 10px -10px 30px #feec85, -20px -20px 40px #ffae34, 20px -40px 50px #ec760c, -20px -60px 60px #cd4606, 0 -80px 70px #973716, 10px -90px 80px #451b0e;
  
}
  
[/css]

За эффект огня отвечает аттрибут text-shadow. Смело поэкспериментируйте с цветами, чтобы понять, за что отвечает конкретный параметр.

Демо доступно на <a href="http://codepen.io/4gray/pen/pcgde" target="_blank">Codepen</a>.