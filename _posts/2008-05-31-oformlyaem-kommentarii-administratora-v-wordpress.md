---
id: 338
title: Оформляем комментарии администратора в WordPress
date: 2008-05-31T15:34:56+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=338
permalink: /wordpress/oformlyaem-kommentarii-administratora-v-wordpress/
ljID:
  - 199
prosmotr:
  - 1025
wpb_post_views_count:
  - 1745
dsq_thread_id:
  - 1565021935
categories:
  - wordpress
tags:
  - wordrpess
---
<img class="alignright size-thumbnail wp-image-339" style="float: right;" title="wordpress" src="{{site.img_cdn}}/wordpress-100x100.png" alt="wordpress" width="100" height="100" />Навеяно постом из блога <a href="http://nettuts.com/news/unraveling-the-secrets-of-wordpress-commentsphp-file/" target="_blank">Nettuts</a>, где подробно описана каждая строчка файла comments.php. Собственно Вы наверное не раз видели что во многих блогах комментарий владельца оформлены подругому и отличаются от комментариев всех других участников.

<!--more-->

Погуглив я нашел несколько вариантов для реализаций, но больше всего мне понравился вариант от <a href="http://5thirtyone.com/archives/774" target="_blank">5thirtyone.</a>

<a href="http://5thirtyone.com/archives/774" target="_blank"></a>Чтож начнем:

1. В первую очередь заходим в папку с шаблоном и открываем comments.php

2. Находим в нем строчку:

> `<li class="<?php echo $oddcomment; ?>" id="comment-<?php comment_ID() ?>">`

И заменяем её этой строкой:

> `<li class="<?php if ($comment->comment_author_email == "вашemail@domain.com") echo 'admin'; else echo $oddcomment; ?> item" id="comment-<?php comment_ID() ?>">`

Здесь нужно будет изменить email адрес &#8220;вашemail@domain.com&#8221; на почту администратора(тот адрес что стоит в профиле админа в wordpress). Так же можно изменить класс admin и тег <li> (например на <div>), но это уже зависит от оформления.

3. Ну и наконец открываем style.css создаем там наш класс .admin { } и прописываем в нем все нужные параметры.

_+ Для вдохновения: <a href="http://www.blogdesignblog.com/blog-design/30-comment-designs-for-webdesigners/" target="blank">30 Must See Comment Designs for Web Designers</a>_