---
id: 1819
title: Оптимизация сайта для для Iphone/iPod/iPad (добавляем иконку и сообщение приветствия)
date: 2011-03-24T23:47:28+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=1819
permalink: /stati/optimizaciya_saita_dlya_iphone_ipad_ipod/
ljID:
  - 327
onswipe_thumb:
  - http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/iphone_Desk_icon1.jpg
prosmotr:
  - 508
wpb_post_views_count:
  - 2597
dsq_thread_id:
  - 1570588537
categories:
  - Статьи
tags:
  - ipad
  - iphone
  - ipod
  - Для Wordpress
  - иконка
---
<center>
  <a href="http://artslab.info/wp-content/uploads/iphone_Desk_icon21.jpg"><img src="http://artslab.info/wp-content/uploads/iphone_Desk_icon21-200x300.jpg" alt="иконка сайта для iphone" title="iphone_Desk_icon2" width="200" height="300" class="alignnone size-medium wp-image-1823" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/iphone_Desk_icon21-200x300.jpg 200w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/iphone_Desk_icon21.jpg 320w" sizes="(max-width: 200px) 100vw, 200px" /></a> <a href="http://artslab.info/wp-content/uploads/iphone_Desk_icon1.jpg"><img src="http://artslab.info/wp-content/uploads/iphone_Desk_icon1-200x300.jpg" alt="как установить иконку на сайт для iphone" title="iphone_Desk_icon" width="200" height="300" class="alignnone size-medium wp-image-1822" /></a>
</center>

Хоть в заголовке и присутствуют &#8220;яблочные&#8221; слова, но содержание поста будет наиболее **важным** не для владельцев данных девайсов, а **для нас, вебмастеров**. Сегодня мы займемся **улучшением совместимости** нашего сайта с iPhone/iPad и iPod.

Дело в том что в браузере iPhone, присутствует функция &#8220;+ -> Добавить &#8220;домой&#8221; &#8220;, которая добавляет иконку (с ссылкой на сайт) на домашний экран устройства. Эта самая иконка должна иметь название **apple-touch-icon.png** и путь к ней должен быть прописан, примерно так же, как и к favicon. Размер не имеет значения, я создал 60x60px. _Некоторые рекомендуют 120x120px, но главное чтобы выглядело красиво._

<center>
  <a href="http://artslab.info/wp-content/uploads/apple-touch-icon.png"><img src="http://artslab.info/wp-content/uploads/apple-touch-icon.png" alt="иконка сайта для айфона" title="apple-touch-icon" width="60" height="60" class="alignnone size-full wp-image-1836" /></a>
</center>

Прописывается иконка таким образом:

[sourcecode language=&#8221;html&#8221;]

<link rel="apple-touch-icon" href="путь_к_иконке/apple-touch-icon.png" />
[/sourcecode]


<small>Если же иконка отсутствует, то на её месте будет отображаться стандартный пустой вариант.</small>

> Для тех кто пользуется WordPress рекомендую воспользоватся плагином [WpTouch](http://artslab.info/2010/09/wptouch-mobilnaya-versiya-sayta/), о нем я уже [писал более подробно](http://artslab.info/2010/09/wptouch-mobilnaya-versiya-sayta/). В настройках WpTouch есть отдельная возможность добавить иконку прямо [через админ-интерфейс движка](http://artslab.info/wp-content/uploads/wptouch_add_icon.jpg).

И напоследок еще одна приятная мелочь, те кто заходил с айфона например на мобильную версию сайта vkontakte, наверняка видели такое **всплывающее сообщение**:

<center>
  <a href="http://artslab.info/wp-content/uploads/vkontakte_add2home.jpg"><img src="http://artslab.info/wp-content/uploads/vkontakte_add2home-300x182.jpg" alt="мобильная версия сайта вконтакте" title="vkontakte_add2home" width="300" height="182" class="alignnone size-medium wp-image-1835" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/vkontakte_add2home-300x182.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/vkontakte_add2home.jpg 430w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Добавить к себе на сайт такое pop-up окно, можно с помощью скрипта [Add To Home Screen](http://cubiq.org/add-to-home-screen).

Устанавливается очень просто, [скачиваем файлы](https://github.com/cubiq/add-to-homescreen/tarball/master) и загружаем их к себе на сайт. Затем прописываем настройки скрипта и путь к файлам, на главной странице сайта, а именно перед тегом <head/>:

[sourcecode language=&#8221;html&#8221;]




<link rel="stylesheet" href="path/to/add2home.css" />
[/sourcecode]




<center>
  <a href="http://artslab.info/wp-content/uploads/add2home-screen2.jpg"><img src="http://artslab.info/wp-content/uploads/add2home-screen2-300x167.jpg" alt="add to home iphone popup window" title="add2home-screen2" width="300" height="167" class="alignnone size-medium wp-image-1840" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/add2home-screen2-300x167.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/add2home-screen2.jpg 324w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

В строке &#8220;message:&#8221; содержится текст всплывающего окна, его можно заменить на свои, либо удалить эту строка, тогда там будет отбражатся стандартное сообщение.