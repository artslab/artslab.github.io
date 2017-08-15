---
id: 344
title: Вкладки на jQuery
date: 2008-06-14T19:15:14+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=344
permalink: /news/vkladki-na-jquery/
ljID:
  - 201
prosmotr:
  - 205
wpb_post_views_count:
  - 1609
dsq_thread_id:
  - 1565022454
categories:
  - skriptyi
tags:
  - javascript
  - jquery
  - js
---
<p align="center">
  <img class="alignnone size-full wp-image-345 aligncenter" title="tabs" src="{{site.img_cdn}}/tabs.jpg" alt="Вкладки на jQuery" width="421" height="326" srcset="{{site.img_cdn}}/tabs.jpg 421w, {{site.img_cdn}}/tabs-300x232.jpg 300w" sizes="(max-width: 421px) 100vw, 421px" />
</p>

В последнее время во многих блогах стали использовать вкладки для навигации. Во первых для экономии места, а во вторых просто для красивого вида. Далее описан простой процес создания таких вкладок при помощи <a href="http://jquery.com/" target="_blank">jQuery</a>.<!--more-->

**Установка:**

1. Скачиваем архив с <a href="http://www.box.net/shared/sw1it78cgg" target="_blank">файлами</a>

2. Прописываем путь к ним в области между <head> и </head>:

[sourcecode language=&#8217;html&#8217;]




<link rel=”stylesheet” href=”style.css” type=”text/css” media=”screen” /> [/sourcecode]

3. Добавляем сами вкладки на страницу, следующим образом:

[sourcecode language=&#8217;html&#8217;] <div class=”tabs”> <!– tabs –><ul class=”tabNavigation”>

  * <a href=”#first”>Первая</a>
  * <a href=”#second”>Вторая</a>
  * <a href=”#third”>Третья</a></ul>

<!– tab containers –><div id=”first”>

Содержание первой вкладки</div> <div id=”second”>

Содержание второй вкладки</div> <div id=”third”>

Содержание третьей вкладки</div> </div>

[/sourcecode]

<a href="http://artslab.info/demo/jquerytabs/" target="_blank">Посмотреть демо</a> <a href="http://jqueryfordesigners.com/jquery-tabs/" target="_blank">Источник</a> <span style="color: #888888;"></span></blockquote>