---
id: 4783
title: Как быстро вставить анонс iOS-приложения из AppStore в блог (WP)
date: 2012-08-26T13:04:27+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=4783
permalink: /wordpress/kak-bystro-vstavit-anons-ios-prilozheniya-iz-appstore-v-blog-wp/
prosmotr:
  - 38
wpb_post_views_count:
  - 1413
dsq_thread_id:
  - 1565022154
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
categories:
  - Для Wordpress
tags:
  - ios
  - Для Wordpress
  - плагин
---
<center>
  <a href="http://img.artslab.info/appstore_wordpress.png"><img src="http://img.artslab.info/appstore_wordpress-300x196.png" alt="плагин для вставки информации о приложений из AppStore" title="appstore_wordpress" width="300" height="196" class="aligncenter size-medium wp-image-4981" srcset="http://img.artslab.info/appstore_wordpress-300x196.png 300w, http://img.artslab.info/appstore_wordpress.png 640w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Речь идет о плагине для WordPress &#8211; [AppStore Links](http://wordpress.org/extend/plugins/appstore/), который позволит вставит анонс приложения из магазина AppStore в пост. В таком анонсе отображается иконка приложения, разработчик, цена, скриншоты и конечно же ссылка. Думаю, те кто регулярно публикуют обзоры iOS-приложений оценят этот плагин, так как он позволит сэкономить много времени.

Есть несколько видов для отображения анонса: короткий &#8211; с иконкой, ценой и ссылкой или расширенный &#8211; включает в себя еще и скриншоты приложения. Кроме того есть возможность, вывести отдельно только скриншоты.

<!--more-->

**Пример и использование:**

Для демонстраций плагина возьмем приложение [IncrediBooth](http://itunes.apple.com/us/app/incredibooth/id378754705), которое представляет из себя фотоавтомат для iOS, в рамках акций &#8220;App of the Week&#8221; раздается в данный момент абсолютно бесплатно.

Для короткого анонса, используем тег: 

> &#091;app 378754705&#093;

[app 378754705]

_Цифры в тегах, это id, который можно скопировать из ссылки на приложение в AppStore._

Тег для вставки расширенного блока:

> &#091;appext 378754705&#093;

[appext 378754705]

Для того чтобы вывести только скриншоты:

> &#091;appimg 378754705&#093;

[appimg 378754705]