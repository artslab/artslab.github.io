---
id: 7648
title: 'WP-Appbox &#8211; создаст красивые анонсы приложений в записях'
date: 2013-08-29T13:29:30+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7648
permalink: /wordpress/wp-appbox-sozdast-krasivye-anonsy-prilozhenij-v-zapisyax/
cover:
  - 7809
wpb_post_views_count:
  - 2860
dsq_thread_id:
  - 1666620147
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
categories:
  - wordpress
tags:
  - wordpress
  - плагин
---
<center>
  <a href="{{site.img_cdn}}/preview_plugin.png"><img src="{{site.img_cdn}}/preview_plugin-300x202.png" alt="обзор приложения" class="aligncenter size-medium wp-image-7671" srcset="{{site.img_cdn}}/preview_plugin-300x202.png 300w, {{site.img_cdn}}/preview_plugin.png 632w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Хочу поделиться отличным WordPress-плагином для блоггеров, которые регулярно пишут о различных мобильных приложениях, плагинах и дополнениях для браузеров. <a href="http://wordpress.org/plugins/wp-appbox/" target="_blank">WP-Appbox</a> позволит легко добавить красивый контейнер с ссылкой, скриншотами и короткой информацией о приложений/дополнений.

<!--more-->

Недавно плагин обновился до второй версий и теперь поддерживает целый ряд магазинов с приложениями:

  * Amazon App Shop
  * AndroidPit (Android)
  * App Store & Mac App Store
  * Chrome Web Store
  * Firefox Add-ons
  * Firefox Marketplace
  * Google Play Store
  * Intel AppUp
  * Opera Add-ons
  * Samsung Apps (Android)
  * Steam (приложения без возрастных ограничений)
  * Windows Store
  * Windows Phone Store
  * WordPress-Plugins



В WP-Appbox доступны три разных вида контейнеров для визуального оформления &#8211; simple, screenshots и banner. Для того чтобы вставить бокс в запись, необходимо воспользоваться следующим кодом:

<pre>&#91;appbox storename app-id format&#93;</pre>

Например:

<pre>&#91;appbox appstore 574375380 screenshots&#93;</pre>

Запоминать код не потребуется, так как после установки и активаций плагина кнопочки для его вставки появятся в визуальном редакторе WordPress.

<center>
  <img src="{{site.img_cdn}}/appbox_knopki.png" alt="кнопки плагина в WYSIWYG редакторе" class="aligncenter wp-image-7703" srcset="{{site.img_cdn}}/appbox_knopki.png 554w, {{site.img_cdn}}/appbox_knopki-300x44.png 300w" sizes="(max-width: 554px) 100vw, 554px" />
</center>

Напоследок, демо Appbox в расширенном формате (screenshots) с ссылкой на игрушку Sky Gamblers для iOS, которую в данный момент раздают бесплатно 😉

[appbox appstore 574375380 screenshots]

И в коротком формате (simple)

[appbox appstore 655527928 simple]