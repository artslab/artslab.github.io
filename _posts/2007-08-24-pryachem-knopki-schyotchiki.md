---
id: 100
title: Прячем кнопки счётчики
date: 2007-08-24T23:46:16+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=100
permalink: /stati/pryachem-knopki-schyotchiki/
ljID:
  - 75
prosmotr:
  - 118
wpb_post_views_count:
  - 1241
dsq_thread_id:
  - 1565018603
categories:
  - stati
tags:
  - coding
  - css
  - html
---
<center>
  <a href="{{site.img_cdn}}/hide_counters.png"><img src="{{site.img_cdn}}/hide_counters.png" alt="как спрятать кнопки счетчиков" title="hide_counters" width="250" height="181" class="alignnone size-full wp-image-1831" /></a>
</center>

По тем или иным причинам, **код счётчиков** систем интернет-статистики зачастую приходится **скрывать** на странице. Оставим в стороне правомерность этого действия (читайте внимательно правила конкретного счётчика) и рассмотрим способы сокрытия.

Самый тривиальный способ, который я, должен признать, долгое время использовал, не ведая о его недостатках:

<!--more-->

> <div style=&#8221;display:none&#8221;>

> <!&#8211; SuperLog &#8211;>

> код счётчика

> <!&#8211; /SuperLog &#8211;>

> </div>

Всё очень просто — с помощью свойства <a href="http://www.w3.org/TR/CSS21/visuren.html#propdef-display" title="display" target="_blank">display</a> мы убираем из layout&#8217;а страницы код счётчика, при этом Internet Explorer и Mozilla всё равно обрабатывают этот код и загружают спрятанную картинку-счётчик.

Как оказалось [из небольшой, но ценной дисскусии](http://imfo.ru/archive/2004/01/29/display_none_invisible_counter "Обсуждение"), Opera и Safari не загружают картинку-счётчик. Это плохо, т. к. в таком случае мы теряем некоторых посетителей.

В итоге родился такой вот CSS класс (несколько избыточный, но да будет так), который устраивает все современные браузеры:

> div.stats{

> display:inline;

> height:0px;

> left:-1000px;

> margin:0px;

> padding:0px;

> position:absolute;

> top:-1000px;

> visibility:hidden;

> width:0px

> }

В HTML (желательно, сразу после _body_) пишем таким образом:

> <div class=&#8221;stats&#8221;>

> <!&#8211; SuperLog &#8211;>

> код счётчика

> <!&#8211; /SuperLog &#8211;>

> </div>

P. S. Дмитрий Полубояринов предлагает ещё один вариант прятания счетчиков: вместо вписывания посредством _document.write_ рисунка в документ, можно создать объект _Image_ и подгрузить в него рисунок.

Было:

> document.write(&#8216;<a href=&#8221;http://click.superlog.ru/&#8221;><img &#8216;+&#8217;src=&#8221;http://hit.superlog.ru/cgi-bin/superlog/count?&#8217;+superlog_r+'&#8221; border=&#8221;0&#8243; width=&#8221;88&#8243; height=&#8221;31&#8243; alt=&#8221;SuperLog&#8221;></a>&#8217;);

Стало:

> cntHL_Img=new Image;

> cntHL\_Img.src=&#8217;http://hit.superlog.ru/cgi-bin/superlog/count?&#8217;+superlog\_r;

>
**Автор: <a href="http://htmlcoder.visions.ru/About/#author" tooltip="Информация об авторе">Александр Шуркаев</a>, &#8220;[Заметки HTML кодера](http://htmlcoder.visions.ru/)&#8220;**