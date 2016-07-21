---
id: 3181
title: Создание страницы архива блога WordPress
date: 2011-05-27T14:40:28+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=3181
permalink: /wordpress/sozdanie-stranicy-arxiva-bloga-wordpress/
ljID:
  - 404
prosmotr:
  - 216
wpb_post_views_count:
  - 1789
dsq_thread_id:
  - 1565016838
categories:
  - Для Wordpress
tags:
  - Для Wordpress
---
Если регулярно вести блог, то рано или поздно в нем появится большое количество записей и чтобы облегчить доступ к ним, лучше всего создать страницу с архивом. Однажды я уже публиковал [код для создания такой страницы](http://artslab.info/wordpress/sozdanie-stranitsyi-arhiva-v-wordpress/), тогда я просто предлагал вывести заголовки всех постов с датой. Но на тот момент постов в моем блоге было не так много как сейчас&#8230; 

Поэтому я решил вывести список месяцев определенного года и список категорий, где в скобках указано количество записей. 

<center>
  <a href="http://img.artslab.info/archive_page.jpg"><img src="http://img.artslab.info/archive_page-300x167.jpg" alt="страница архива блога на wordpress" title="archive_page" width="300" height="167" class="alignnone size-medium wp-image-3184" srcset="http://img.artslab.info/archive_page-300x167.jpg 300w, http://img.artslab.info/archive_page.jpg 535w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

## Как сделать такую страницу архива?

<!--more-->

Несомненно можно воспользоваться каким-нибудь плагином, но я не стал, сделал в ручную.
  
Открываем папку с вашей темой и создаем там файл archives.php.
  
Открываем его и вставляем в него следующий код:

[sourcecode language=&#8221;php&#8221;]
  
<?php
/*
Template Name: Archive
*/
?>


  
<?php get_header(); ?>

# Архив

## По месяцам

<?php wp_get_archives('show_post_count=1'); ?>



## По категориям

<?php wp_list_cats('hierarchical=0&#038;optioncount=1&#038;show_count=1'); ?>

<?php get_sidebar(); ?>


  
<?php get_footer(); ?>[/sourcecode]

После этого создаем страницу и в виде шаблона выбираем Archives page.

<center>
  <img src="http://img.artslab.info/archive.jpg" alt="архив сайта" title="archive" width="297" height="246" class="alignnone size-full wp-image-3183" />
</center>

Готово!