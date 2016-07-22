---
id: 7523
title: Выпадающее меню на чистом CSS
date: 2013-08-25T22:57:32+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7523
permalink: /snippety/vypadayushhee-menyu-na-chistom-css/
cover:
  - 8065
wpb_post_views_count:
  - 2795
dsq_thread_id:
  - 1647817896
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
  - html
  - меню
  - сниппет
---
Продолжим развлекаться с менюшками и сегодня создадим простое выпадающее меню на чистом CSS&HTML. В прошлых записях мы уже рассматривали два других варианта меню &#8211; [адаптивное](http://artslab.info/snippety/sozdaem-adaptivnoe-menyu/ "Создаем адаптивное меню") и [фиксированное меню](http://artslab.info/snippety/sozdaem-fiksirovannoe-navigacionnoe-menyu-otobrazhaemoe-pri-prokrutke-stranicy/ "Создаем фиксированное навигационное меню, отображаемое при прокрутке страницы").

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css-300x188.png" alt="выпадающее меню на чистом CSS" class="aligncenter size-medium wp-image-7532" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css-300x188.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css.png 581w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

Перед тем как приступить, предлагаю сразу взглянуть на конечный результат (<a href="http://codepen.io/4gray/pen/CoyJt" target="_blank">Codepen</a>).

### 1. HTML код

[html]

<ul id="menu">

<li><a href="#">Главная</a></li>

<li><a href="#">Категории</a>

<ul>

<li><a href="#">Ссылка 1</a></li>

<li><a href="#">Ссылка 2</a></li>

<li><a href="#">Ссылка 3</a></li>

</ul>

</li>

<li><a href="#">О сайте</a>

<ul>

<li><a href="#">Ссылка 1</a></li>

</ul>

</li>

<li><a href="#">Контакт</a></li>

</ul>

[/html]

Создадим обычный список (Unordered List) и добавим к двум пунктам &#8211; субменю в виде еще двух вложенных списков.

### 2. CSS

[css]

#menu {

background: #c0392b;

width: 100%;

padding:0;

text-align: center;

float:left;

border-bottom: 6px solid #e74c3c;

}

#menu a {

color: #fff;

text-decoration: none;

}

#menu a:hover {

color: #ccc;

}

#menu ul {

padding:0;

margin:0;

}

#menu li {

list-style: none;

padding: 0 15px 0 0;

width:100px;

margin: 0 auto;

float:left;

line-height: 50px;

}

#menu li ul {

position:absolute;

display: none;

}

#menu li ul li {

float: none;

display: inline;

width:100px;

line-height:35px;

}

#menu li ul li:hover {

background: #c0392b;

}

#menu li:hover ul {

display:block;

}

#menu li ul li {

display: block;

background:#e74c3c;

}

[/css]

Главное, на что стоит обратить внимание в CSS части, то что выпадающее меню изначально скрыто (display:none) и появляется только при наведения курсора (li:hover ul).

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css-300x188.png" alt="выпадающее меню на чистом CSS" class="aligncenter size-medium wp-image-7532" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css-300x188.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/dropdown_menu_css.png 581w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Поэкспериментировать с кодом можно, как всегда, в песочнице на <a href="http://codepen.io/4gray/pen/CoyJt" target="_blank">Codepen</a>.