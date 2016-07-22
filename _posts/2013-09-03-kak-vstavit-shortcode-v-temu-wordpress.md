---
id: 7815
title: Как вставить shortcode в тему WordPress?
date: 2013-09-03T20:24:13+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7815
permalink: /snippety/kak-vstavit-shortcode-v-temu-wordpress/
cover:
  -
wpb_post_views_count:
  - 1066
dsq_thread_id:
  - 1703563053
categories:
  - Сниппеты
tags:
  - Для Wordpress
  - сниппет
---
Многие плагины используют короткий код (shortcode) для их интеграций в систему. Такой код можно легко добавить в пост, либо на страницу. Но что делать если плагин необходимо разместить в другом месте и необходимо добавить этот код в файлы темы. Если просто вставить такой код в его обычном виде теме, то он не будет обработан системой и отобразиться как простой текст.

<!--more-->

Для того чтобы добиться нужного эффекта и правильно встроить плагин на ваш сайт, нам на помощь придет PHP-функцией do_shortcode(). Именно, благодаря ей WordPress интерпретирует короткий код.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/shortcode_v_wp.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/shortcode_v_wp-300x86.png" alt="короткий код" class="aligncenter size-medium wp-image-7816" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/shortcode_v_wp-300x86.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/shortcode_v_wp.png 622w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

### Код:

{% highlight php %}<?php echo do\_shortcode("[your\_shortcode]"); ?>{% endhighlight %}