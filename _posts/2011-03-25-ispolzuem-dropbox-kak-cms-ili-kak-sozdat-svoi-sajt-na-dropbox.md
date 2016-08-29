---
id: 1851
title: Используем Dropbox как хостинг для сайта или как создать свои сайт на Dropbox
date: 2011-03-25T10:10:32+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=1851
permalink: /onlayn-servisyi/ispolzuem-dropbox-kak-cms-ili-kak-sozdat-svoi-sajt-na-dropbox/
ljID:
  - 329
onswipe_thumb:
  - {{site.img_cdn}}/droppages.jpg
prosmotr:
  - 447
cover:
  - 5952
wpb_post_views_count:
  - 2618
dsq_thread_id:
  - 1563728554
categories:
  - onlayn-servisyi
tags:
  - dropbox
  - облако
---
<center>
  <a href="{{site.img_cdn}}/droppages.jpg"><img src="{{site.img_cdn}}/droppages-300x60.jpg" alt="создать свои сайт на dropbox" title="droppages" width="300" height="60" class="alignnone size-medium wp-image-1852" /></a>
</center>

Нравится мне [Dropbox](http://db.tt/RYea5eSO), нравится облачные темы, что-то в этом есть, не просто удобно использовать, но и как то особенно &#8220;вкусно&#8221; нам все это преподносят.

Вот и в данном случае красиво получается&#8230;

Совсем недавно появился сервис [Droppages](http://droppages.com). Смысл заключается в том, что в итоге мы получим свой сайт на [artslab.droppages.com](http://artslab.droppages.com), при этом файлы сайта будут лежать на сервисе Dropbox.

<!--more-->

**Как это сделать?**

<center>
  <a href="{{site.img_cdn}}/kak_nachat.jpg"><img src="{{site.img_cdn}}/kak_nachat-300x82.jpg" alt="как создать сайт на dropbox" title="kak_nachat" width="300" height="82" class="alignnone size-medium wp-image-1853" srcset="{{site.img_cdn}}/kak_nachat-300x82.jpg 300w, {{site.img_cdn}}/kak_nachat-1024x282.jpg 1024w, {{site.img_cdn}}/kak_nachat.jpg 1153w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Во-первых необходимо зарегистрировать себе аккаунт на Dropbox и установить приложение сервиса на компьютер. После этого заходим в папку Dropbox и создаем в ней новую папку &#8220;название\_сайта.droppages.com&#8221;, расшариваем ее(правой кнопкой по папке &#8220;Dropbox -> Share This Folder&#8230;&#8221;) с server1@droppages.com и через некоторое время получаем подтверждение по почте. Заходим по ссылке &#8220;название\_сайта.droppages.com&#8221; и вуаля, заработало!

**Что в этом особенного, кроме поддомена на сайте droppages.com?**

<center>
  <a href="{{site.img_cdn}}/artslab_droppages.jpg"><img src="{{site.img_cdn}}/artslab_droppages-300x295.jpg" alt="пример сайта на droppages" title="artslab_droppages" width="300" height="295" class="alignnone size-medium wp-image-1860" srcset="{{site.img_cdn}}/artslab_droppages-300x295.jpg 300w, {{site.img_cdn}}/artslab_droppages.jpg 809w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

**1. Структура сайта**

На дропбокс всегда можно было загрузить html файл, расшарить его и получилась бы своя страничка, кажется все тоже самое кроме домена второго уровня, но не все так просто.



<center>
  <a href="{{site.img_cdn}}/droppages_box.jpg"><img src="{{site.img_cdn}}/droppages_box-300x144.jpg" alt="структура сайта на droppages" title="droppages_box" width="300" height="144" class="alignnone size-medium wp-image-1855" srcset="{{site.img_cdn}}/droppages_box-300x144.jpg 300w, {{site.img_cdn}}/droppages_box.jpg 429w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



Структура нашего сайта на droppages делится на три папки: **Content, Public и Templates**.

В первой хранится содержание сайта в **текстовых файлах**, стоит отметить разметку сайта, используется &#8211; [Markdown](http://ru.wikipedia.org/wiki/Markdown).

В папке **Public** хранятся js- и css-файлы.

И последняя папка **Templates** cодержит html-шаблоны страниц.

_Кстати, на сайте также доступны готовые шаблоны, правда пока что только их только два._

<center>
  <a href="{{site.img_cdn}}/droppage_themes.jpg"><img src="{{site.img_cdn}}/droppage_themes-300x160.jpg" alt="шаблоны droppages" title="droppage_themes" width="300" height="160" class="alignnone size-medium wp-image-1854" srcset="{{site.img_cdn}}/droppage_themes-300x160.jpg 300w, {{site.img_cdn}}/droppage_themes.jpg 718w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

**2. Удобная синхронизация файлов**

Все файлы лежат в папке на компьютере, которая постоянно синхронизируется с dropbox, а это значит что **бэкап** всегда лежит готовый в папке. Так же не нужно лишний раз запускать фтп клиент, подключаться к серверу. Не нужно заходить в веб-интерфейс, вводить логин и пароль.

**3. Бесплатность сервиса, ЧПУ**

Dropbox дает нам бесплатный хостинг c 10 гб траффика в день + мин. 2 гб дискового пространства. Ну и последнее, не столь важное но приятное &#8211; это ЧПУ, красивые и понятные ссылки.

Итог: Сервис пока что новый и не совсем понятно что будет в будущем, но идея и реализация мне нравится. Подойдет для создания небольших статических сайтов.