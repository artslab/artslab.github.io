---
id: 3718
title: 'Замена плагинов #1 : Удаляем FeedBurner FeedSmith, прописываем редирект вручную'
date: 2011-07-26T23:43:01+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=3718
permalink: /wordpress/zamena-plaginov-1-udalyaem-feedburner-feedsmith-propisyvaem-redirekt-vruchnuyu/
onswipe_thumb:
  - http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/pretty_rss_feed_icon.png
prosmotr:
  - 113
wpb_post_views_count:
  - 967
dsq_thread_id:
  - 1580389030
categories:
  - Для Wordpress
tags:
  - rss
  - Для Wordpress
  - плагин
---
Я недавно публиковал [список плагинов](http://artslab.info/news/30-plaginov-dlya-wordpress-kotorye-ispolzuyutsya-v-etom-bloge/), которые я использую в этом блоге. Таких набралось аж более 30 штук, что дает неплохую нагрузку на хостинг. Поэтому в целях оптимизации блога, я решил сократить этот длинный список, а функционал попытаться реализовать вручную, там где это возможно.

Начнем с малого и простого, с плагина [FeedBurner FeedSmith](http://wordpress.org/extend/plugins/feedburner-plugin/). Как известно, это дополнение отвечает за редирект с простого фида блога (site.ru/feed) на ленту Feedburner (feeds.feedburner.com/feedname). Реализовать такой редирект, можно легко и без помощи дополнительного плагина. Для этого необходимо открыть файл .htaccess и добавить в него эти строки:

[sourcecode language=&#8221;php&#8221;]# redirect wordpress feed to feedburner

<IfModule mod_rewrite.c>

RewriteEngine on

RewriteCond %{HTTP\_USER\_AGENT} !FeedBurner [NC]

RewriteCond %{HTTP\_USER\_AGENT} !FeedValidator [NC]

RewriteRule ^feed/?([_0-9a-z-]+)?/?$ http://feeds.feedburner.com/feedname [R=302,NC,L]

</IfModule>[/sourcecode]

Главное, не забудьте сменить ссылку на адрес вашей RSS-ленты на Feedburner.

-1 плагин, дальше больше 🙂