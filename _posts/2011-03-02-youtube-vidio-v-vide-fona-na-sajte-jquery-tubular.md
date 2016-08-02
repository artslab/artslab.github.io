---
id: 1678
title: 'Youtube-видео в виде фона на сайте &#8211; jQuery Tubular'
date: 2011-03-02T03:06:28+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=1678
permalink: /skriptyi/youtube-vidio-v-vide-fona-na-sajte-jquery-tubular/
ljID:
  - 317
prosmotr:
  - 374
wpb_post_views_count:
  - 2235
dsq_thread_id:
  - 1563659952
categories:
  - skriptyi / CMS
tags:
  - jquery
  - js
  - video
  - youtube
---
<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/tubular.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/tubular.png" alt="добавить видео с youtube на фон сайта" title="tubular" width="166" height="81" class="alignnone size-full wp-image-1679" /></a>
</center>

Наткнулся на интересный jQuery скрипт, который позволяет вставить **видео в виде фона для сайта**. Впечатляет, не правда ли? Как по мне, то сама идея немного необыкновенна, но вот другой вопрос, найдет ли этот скрипт реальное применение&#8230;

Рабочий пример можно посмотреть на [сайте разработчика](http://www.seanmccambridge.com/tubular/), а скачать **jQuery Tubular** можно со страницы проекта на [Google Code](http://code.google.com/p/jquery-tubular/).

**Использование скрипта:**

1. Перед тегом </head>, добавить:

[sourcecode language=&#8221;html&#8221;]





[/sourcecode]

2. В файле mission-control.js, во второй строке, прописываем id видеоролика с youtube:

[sourcecode language=&#8221;javascript&#8221;]$(&#8216;body&#8217;).tubular(&#8216;\_VKW\_M_uVjw&#8217;,&#8217;wrapper&#8217;);[/sourcecode]

_PS: В архиве со скриптом, есть готовый пример._