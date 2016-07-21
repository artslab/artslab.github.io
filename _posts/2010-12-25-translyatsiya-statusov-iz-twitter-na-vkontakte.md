---
id: 632
title: Трансляция статусов из Twitter на Vkontakte
date: 2010-12-25T22:56:39+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=632
permalink: /skriptyi/translyatsiya-statusov-iz-twitter-na-vkontakte/
ljID:
  - 272
prosmotr:
  - 294
wpb_post_views_count:
  - 1077
dsq_thread_id:
  - 1597172768
categories:
  - Скрипты / CMS
tags:
  - twitter
  - vkontakte
  - скрипт
---
<p style="text-align: left;">
  <center>
    <img class="aligncenter" title="vtweet" src="http://artslab.info/wp-content/uploads/vtweet.jpg" alt="из твиттера вконтакт" width="430" height="121" />
  </center>
</p>

Вконтакте есть функция экспорта статусов в twitter, но отсутствует обратное, т.е. функция импорта. Существует приложение, которое импортирует обновления из твиттера, но минус в том, что его необходимо постоянно запускать вручную. То есть никакого официального решения нету, поэтому придется воспользоваться сторонней разработкой.

Скрипт называется [tvkontakte 0.1i](http://kichrum.org.ua/combine-vkontakte-twitter-php-17-07-2009.html), а скачать его можно с [блога автора](http://kichrum.org.ua/combine-vkontakte-twitter-php-17-07-2009.html/vtweet-2). Для правильной работы скрипта необходимо иметь хостинг с поддержкой cronjob и php.

Установка:

> 1. Загружаем скрипт на хостинг
  
> 2. Ставим права 777 на текстовый файл vtweet.txt
  
> 3. Открываем конфигурационный файл vtweet.php и вписываем туда свои логин и пароль от профиля vkontakte, а так же логин twitter-аккаунта
  
> 4. Заходим в панель управления хостингом, обычно это cPanel, либо Direct Admin и настраиваем там cronjob для скрипта, то есть указываем как часто/когда, скрипт будет выполнять обновление статуса
  
> 5. Проверяем работу скрипта =)