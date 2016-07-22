---
id: 444
title: Полезные скрипты для Greasemonkey
date: 2010-02-16T23:42:56+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=444
permalink: /rasshireniya-dlya-firefox/poleznyie-skriptyi-dlya-greasemonkey/
ljID:
  - 253
sbg_selected_sidebar:
  - 'a:5:{i:0;s:1:"0";i:1;s:1:"0";i:2;s:1:"0";i:3;s:1:"0";i:4;s:1:"0";}'
sbg_selected_sidebar_replacement:
  - 'a:5:{i:0;s:1:"0";i:1;s:1:"0";i:2;s:1:"0";i:3;s:1:"0";i:4;s:1:"0";}'
prosmotr:
  - 221
wpb_post_views_count:
  - 2760
dsq_thread_id:
  - 1565021216
categories:
   - rasshireniya-dlya-firefox
tags:
  - firefox
  - greasemonkey
  - дополнение к firefox
---
Решил написать небольшой пост в котором хотел бы поделиться несколькими скриптами для дополнения к Firefox &#8220;Greasemonkey&#8221;, которые я использую.

1. [Vkontakte Music Download](http://userscripts.org/scripts/show/16985)

Наверное все уже как то приловчились скачивать музыку с соц.сети Вконтакте. Во первых, так как это очень удобно, да и собственно потому что там есть почти любая музыка. Кто-то пользуется плагином [DownloadHelper](https://addons.mozilla.org/ru/firefox/addon/3006) для Firefox, те кто не зарегистрирован там пользуются отдельными сайтами вроде vpleer.ru и др. Я же использую связку скрипта [Vkontakte Music Download](http://userscripts.org/scripts/show/16985) для Greasemonkey для скачивания музыки с Вконтакте и DownloadHelper для скачивания медиа-файлов с других сайтов.

<p style="text-align: center;">
  <a href="http://artslab.info/wp-content/uploads/vko_pic.jpg"><img class="size-medium wp-image-447  aligncenter" title="vko_pic" src="http://artslab.info/wp-content/uploads/vko_pic-300x96.jpg" alt="" width="300" height="96" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/vko_pic-300x96.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/vko_pic.jpg 425w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</p>

2. [Greased Lightbox](http://userscripts.org/scripts/show/35377)

Добавляет Lightbox к результатам поиска картинок Google, Flickr, Facebook, Wikipedia, MySpace, deviantART, FFFFOUND! и др.

Выглядит примерно так:

<p style="text-align: center;">
  <a href="http://artslab.info/wp-content/uploads/greased_lightbox.jpg"><img class="size-medium wp-image-446  aligncenter" title="greased_lightbox" src="http://artslab.info/wp-content/uploads/greased_lightbox-300x212.jpg" alt="" width="300" height="212" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/greased_lightbox-300x212.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/greased_lightbox.jpg 808w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</p>

<!--more-->3.

[faviconize-google](http://userscripts.org/scripts/show/58177)

Скрипт добавляет фавиконы на страницус результатами поиска Google. Мелочь, но приятно и облегчает поиск.

<p style="text-align: center;">
  <img class="aligncenter" src="http://github.com/NV/faviconize-google.js/raw/master/screenshot.png" alt="" width="371" height="197" />
</p>

<p style="text-align: left;">
  4. <a href="http://userscripts.org/scripts/show/24371">Favicons for Google Reader</a>
</p>

<p style="text-align: left;">
  Думаю тут все понятно из названия, небольшое украшение для Google Reader. Скрипт добавляет фавиконы к списку подписок.
</p>

<p style="text-align: center;">
  <img class="aligncenter" src="http://img143.imageshack.us/img143/8993/greaderwg2.png" alt="" width="269" height="236" />
</p>

<p style="text-align: left;">
  5. <a href="http://userscripts.org/scripts/show/24430">Gmail Favicon Alerts 3</a>
</p>

<p style="text-align: left;">
  Данный скрипт заменяет фавикон gmail&#8217;a в вкладках вашего браузера и оповещает о количестве новых, непрочитанных писем.
</p>

<p style="text-align: center;">
  <img class="aligncenter" src="http://peterwooley.com/projects/greasemonkey/gmailfaviconalerts/3.0/unread.jpg" alt="" width="108" height="24" />
</p>

<p style="text-align: left;">
  <em>+ Экспорт Дней рождения из вКонтакте в Google Calendar, реализовано с помощью Gresemonkey, подробнее об этом <a href="http://habrahabr.ru/blogs/GreaseMonkey/75966/">в статье на хабре</a></em>
</p>

<div id="greasedLightboxOverlay">
  <div id="greasedLightbox">
    <img id="greasedLightboxImage" alt="" />
  </div>
</div>

<p id="greasedLightboxErrorContext">
  <p>
    <img id="greasedLightboxPreload" alt="" /><img id="greasedLightboxPrefetch" alt="" />
  </p>