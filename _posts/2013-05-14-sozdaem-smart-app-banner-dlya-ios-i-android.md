---
id: 7112
title: Создаем Smart App Banner для iOS и Android
date: 2013-05-14T18:05:42+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7112
permalink: /stati/sozdaem-smart-app-banner-dlya-ios-i-android/
cover:
  - 
wpb_post_views_count:
  - 3662
dsq_thread_id:
  - 1564966332
categories:
  - Статьи
tags:
  - android
  - ios
  - jquery
  - js
---
<center>
  <a href="http://img.artslab.info/smartapp_banner_sozdat.jpg"><img src="http://img.artslab.info/smartapp_banner_sozdat-300x122.jpg" alt="smart app для ios" class="aligncenter size-medium wp-image-7113" srcset="http://img.artslab.info/smartapp_banner_sozdat-300x122.jpg 300w, http://img.artslab.info/smartapp_banner_sozdat.jpg 600w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Если Вы впервые сталкиваетесь с термниом Smart App Banners, то одного взгляда на скриншот хватит для того чтобы понять, о чем идет речь. Думаю что все пользователи iOS или Android, хотя бы раз встречали такой вид баннера на каком-либо сайте. Smart App Banner это небольшая панелька, которая появляется в верхней части страницы и призывает пользователя установить приложение. Для сайтов имеющих свое нативное приложение в AppStore или Google Play это отличный способ для его рекламы. 
  
Сегодня я хотел бы рассказать вам о том, как создать такую панельку и закрепить ее на страничке.

<!--more-->


  
**1. iOS**

Начнем с iOS, так как создать Smart Banner App для пользователей мобильных на этой системы, очень-очень просто. Для этого нам понадобиться узнать только id необходимого приложения в AppStore и добавить всего одну мета-строку в header сайта:

[html]<meta name="apple-itunes-app" content="app-id=%айди_приложения%">[/html]
  
<small>%айди_приложения% &#8211; заменить на настоящий</small>

Для того чтобы проверить результат, откройте сайт в браузере Safari (только Safari понимает этот метатег, для других браузеров используем плагин [jQuery Smart Banner](http://jasny.github.io/jquery.smartbanner/)) на iPhone/iPad или через iOS-симулятор.

<center>
  <a href="http://img.artslab.info/smartapp_banner_sozdat.jpg"><img src="http://img.artslab.info/smartapp_banner_sozdat-300x122.jpg" alt="smart app для ios" class="aligncenter size-medium wp-image-7113" srcset="http://img.artslab.info/smartapp_banner_sozdat-300x122.jpg 300w, http://img.artslab.info/smartapp_banner_sozdat.jpg 600w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

**2. Android**

Для андроида, придется воспользоваться небольшим jQuery-плагином &#8211; [jQuery Smart Banner](http://jasny.github.io/jquery.smartbanner/). Примеры с кодом доступны на страничке с плагином.

<center>
  <a href="http://img.artslab.info/smartapp_dlya_android.jpg"><img src="http://img.artslab.info/smartapp_dlya_android-300x76.jpg" alt="smart app banner для андроид приложения" class="aligncenter size-medium wp-image-7115" srcset="http://img.artslab.info/smartapp_dlya_android-300x76.jpg 300w, http://img.artslab.info/smartapp_dlya_android.jpg 707w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

**Для сайтов на основе WordPress**

Конечно же, для тех кто используют вордпресс, доступны готовые плагины, которые активируют смарт баннеры на сайте.Два самых популярных [Smart App Banners](http://wordpress.org/extend/plugins/smart-app-banners/) и [Smart App Banner](http://wordpress.org/extend/plugins/smart-app-banner/)