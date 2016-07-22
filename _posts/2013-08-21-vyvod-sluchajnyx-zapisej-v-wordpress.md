---
id: 7478
title: Вывод случайных записей в WordPress
date: 2013-08-21T14:25:47+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7478
permalink: /snippety/vyvod-sluchajnyx-zapisej-v-wordpress/
cover:
  -
wpb_post_views_count:
  - 995
dsq_thread_id:
  - 1628522580
categories:
  - Сниппеты
tags:
  - php
  - Для Wordpress
---
<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/sluchainie_zapisi_wordpress.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/sluchainie_zapisi_wordpress.png" alt="сниппеты для wordpress" class="aligncenter wp-image-7479" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/sluchainie_zapisi_wordpress.png 355w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/sluchainie_zapisi_wordpress-300x186.png 300w" sizes="(max-width: 355px) 100vw, 355px" /></a>
</center>

Этот небольшой сниппет позволит вывести случайное количество записей из блога в любом месте на Вашем сайте.

<!--more-->

Код можно разместить в любом месте в Вашей теме. Например, если необходимо отобразить список с случайными записями в боковой панели, тогда добавьте его в файл sidebar.php.

### Код:

[php]

<h2>Случайные записи из блога</h2>

<ul>

<?php

$rand\_posts = get\_posts(&#8216;numberposts=5&orderby=rand&#8217;);

foreach( $rand_posts as $post ) :

?>

<li><a href="<?php the\_permalink(); ?>"><?php the\_title(); ?></a></li>

<?php endforeach; ?>

</ul>

[/php]

Как видите, в коде нет ничего сложного. С помощью функций get_posts() мы получаем необходимое количество записей и затем выдаем их поочередно, в виде обычного списка.

_numberposts=5_ обозначает что на сайте будут отображаться 5 случайно выбранных записей.