---
id: 7859
title: Создаем размытый текст (CSS)
date: 2013-09-08T20:46:12+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7859
permalink: /snippety/sozdaem-razmytyj-tekst-css/
cover:
  -
wpb_post_views_count:
  - 1603
dsq_thread_id:
  - 1734149169
categories:
  - Сниппеты
tags:
  - css
  - сниппет
---
Очередной CSS сниппет позволяющий создать размытый текст (blurry text). Добавим немного анимаций при наведении на текст для того чтобы размытый текст плавно переходил в четкую типографию.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/razmitii_tekst.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/razmitii_tekst-300x64.png" alt="размытие текста на css" class="aligncenter size-medium wp-image-7860" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/razmitii_tekst-300x64.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/razmitii_tekst.png 580w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

Код:

[css title=&#8221;style.css&#8221;]

h2 {

color: transparent;

text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);

font-size: 62px;

-webkit-transition: text-shadow 2.0 ease-out;

-moz-transition: text-shadow 2.0 ease-out;

-ms-transition: text-shadow 2.0 ease-out;

-o-transition: text-shadow 2.0 ease-out;

transition: text-shadow 2.0 ease-out;

}

h2:hover {

text-shadow: 0 0 0 rgba(0, 0, 0, 1);

-webkit-transition: text-shadow 0.5s;

-moz-transition: text-shadow 0.5s;

-ms-transition: text-shadow 0.5s;

-o-transition: text-shadow 0.5s;

transition: text-shadow 0.5s;

cursor: default;

}

[/css]

Демо:

<p data-height="268" data-theme-id="414" data-slug-hash="gBAsk" data-user="4gray" data-default-tab="result" class='codepen'>
  See the Pen <a href='http://codepen.io/4gray/pen/gBAsk'>Blurry Text</a> by 4gray (<a href='http://codepen.io/4gray'>@4gray</a>) on <a href='http://codepen.io'>CodePen</a>
</p>