---
id: 352
title: Создание страницы архива в WordPress
date: 2008-06-27T23:25:21+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=352
permalink: /wordpress/sozdanie-stranitsyi-arhiva-v-wordpress/
ljID:
  - 204
prosmotr:
  - 578
wpb_post_views_count:
  - 2872
dsq_thread_id:
  - 1564126900
categories:
  - Для Wordpress
tags:
  - Для Wordpress
---
<p style="text-align: center;">
  <a href="http://img.artslab.info/archiv.png"><img src="http://img.artslab.info/archiv-300x300.png" alt="архив новостей блога" title="archiv" width="300" height="300" class="aligncenter size-medium wp-image-4990" srcset="http://img.artslab.info/archiv-300x300.png 300w, http://img.artslab.info/archiv-100x100.png 100w, http://img.artslab.info/archiv-150x150.png 150w, http://img.artslab.info/archiv.png 713w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</p>

Небольшой мануал, подглянутый у <a href="http://stylizedweb.com/2008/03/08/wp-archive-page/" target="_blank">stylizedweb</a>, по тому, как создать страничку архива сайта в WordPress. С содержанием всех новостей и датой их публикаций, [пример](http://artslab.info/?page_id=350).<!--more-->

1. Для начала нужно сделать копию файла _index.php_ и переименовать её в _archives.php_

2. Затем открываем _archives.php_ и меняем главную часть кода (начинается так же) на это:
  
`<p style="text-align: center;">
  <a href="http://img.artslab.info/archiv.png"><img src="http://img.artslab.info/archiv-300x300.png" alt="архив новостей блога" title="archiv" width="300" height="300" class="aligncenter size-medium wp-image-4990" srcset="http://img.artslab.info/archiv-300x300.png 300w, http://img.artslab.info/archiv-100x100.png 100w, http://img.artslab.info/archiv-150x150.png 150w, http://img.artslab.info/archiv.png 713w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</p>

Небольшой мануал, подглянутый у <a href="http://stylizedweb.com/2008/03/08/wp-archive-page/" target="_blank">stylizedweb</a>, по тому, как создать страничку архива сайта в WordPress. С содержанием всех новостей и датой их публикаций, [пример](http://artslab.info/?page_id=350).<!--more-->

1. Для начала нужно сделать копию файла _index.php_ и переименовать её в _archives.php_

2. Затем открываем _archives.php_ и меняем главную часть кода (начинается так же) на это:
  
` 
  
3. Для того чтобы wordpress распознавал файл _archives.php_ как шаблон, для создания страниц, добавляем в самый верх следующие строчки:
  
`<br />
<?php<br />
/*<br />
Template Name: Archives page<br />
*/<br />
?>`

4. Создаем новую страницу &#8220;Архив&#8221; и в низу, в разделе &#8220;Шаблон страницы&#8221;, выбираем шаблон &#8220;Archives page&#8221;:

<p style="text-align: center;">
  <img class="aligncenter" style="border: 0pt none ;" src="http://clip2net.com/clip/m6048/1214597801-clip-10kb.jpg" alt="создание страницы архива wordpress" width="299" height="134" />
</p>

5. Кликаем по _&#8220;Опубликовать&#8221;_ и готово =)

Источник: <a href="http://stylizedweb.com/2008/03/08/wp-archive-page/" target="_blank">stylizedweb</a>