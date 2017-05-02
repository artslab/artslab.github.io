---
id: 1055
title: Некликабельные ссылки в тексте комментария
date: 2011-01-07T20:11:29+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=1055
permalink: /wordpress/neklikabelnye-ssylki-v-kommentariyax/
ljID:
  - 285
prosmotr:
  - 140
wpb_post_views_count:
  - 712
dsq_thread_id:
  - 1590226210
categories:
  - wordpress
tags:
  - wordpress
  - спам
  - хак
---
Встретил небольшой, но нужный хак для WordPress, который превращает ссылки в тексте комментария в простой текст, то есть делает их некликабельными. Нужно это для того, чтобы защитить свой блог от лишних ссылок и не нужного спама.

Для того, чтобы установить хак, необходимо зайти в папку с темой, открыть файл _functions.php_ и добавить туда одну строку:

[sourcecode language=&#8221;php&#8221;]remove\_filter(&#8216;comment\_text&#8217;, &#8216;make_clickable&#8217;, 9);[/sourcecode]

Сохраняем изменения, готово!

Подглядел [здесь](http://www.wprecipes.com/wordpress-hack-remove-autolinks-in-comments).