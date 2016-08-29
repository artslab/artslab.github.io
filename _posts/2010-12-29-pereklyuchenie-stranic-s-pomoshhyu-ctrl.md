---
id: 631
title: 'Переключение страниц с помощью Ctrl + &larr; / &rarr;'
date: 2010-12-29T18:43:12+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=631
permalink: /skriptyi/pereklyuchenie-stranic-s-pomoshhyu-ctrl/
ljID:
  - 275
prosmotr:
  - 81
wpb_post_views_count:
  - 1119
cover:
  -
dsq_thread_id:
  - 1605140201
categories:
  - skriptyi / CMS
tags:
  - js
  - скрипт
---
<center>
  <a href="{{site.img_cdn}}/navigation.jpg"><img src="{{site.img_cdn}}/navigation.jpg" alt="навигация с помощью ctrl + &larr; / &rarr;" title="navigation" /></a>
</center>

Многие наверняка уже встречали метод навигаций с помощью клавиатуры, а конкретно сочетания клавиш Ctrl + стрелочки влево/вправо. Подобный скрипт используется на многих популярных сайтах, например в поиске на Яндексе, Хабре или сайте студий Лебедева. Такой метод действительно является удобным, так как для постраничной навигаций не нужно использоваться мышь, достаточно одной клавиатуры.

Предлагаю сразу перейти к делу и разобраться с тем, как реализовать такое у себя на сайте:

1. Создаем index.html

[sourcecode lang=&#8221;html&#8221;]<html>

<head>

<script type="text/javascript" src="nav.js"></script>

<link rel="prev" href="page-1.html" id="NextLink" />

<link rel="next" href="page-3.html" id="PrevLink" />

</head>

<body>

<!&#8211; Содержание сайта &#8211;>

<a href="page-1.html">&amp;amp;amp;larr; Назад</a> + <b>Ctrl</b> + <a href="page-3.html">Вперед &amp;amp;amp;rarr;</a>

</body>

</html>

[/sourcecode]<!--more-->

2. Подключаем к нему яваскрипт, для этого создаем файл nav.js

[sourcecode lang=&#8221;javascript&#8221;]

document.onkeydown = NavigateThrough;

function NavigateThrough (event)

{

if (!document.getElementById) return;

if (window.event) event = window.event;

if (event.ctrlKey)

{

var link = null;

var href = null;

switch (event.keyCode ? event.keyCode : event.which ? event.which : null)

{

case 0x25:

link = document.getElementById (&#8216;PrevLink&#8217;);

break;

case 0x27:

link = document.getElementById (&#8216;NextLink&#8217;);

break;

}

if (link &amp;amp;amp;&amp;amp;amp; link.href) document.location = link.href;

if (href) document.location = href;

}

}

[/sourcecode]

3. Открываем наш файл в современном браузере и пробуем переключиться между страницами с помощью &#8220;горячих клавиш&#8221;.

PS: Те кто пользуется стандартным вариантом переключения страниц в WordPress, могут легко прикрутить скрипт к теме.

[Источник](http://designn.org.ua/blog/ru/14.htm)