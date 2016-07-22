---
id: 2636
title: 'Как ускорить скорость загрузки сайта или почему &#8220;тормозит&#8221; мой блог?'
date: 2011-05-20T13:37:01+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=2636
permalink: /wordpress/kak-uskorit-skorost-zagruzki-sajta-ili-pochemu-tormozit-moj-blog/
ljID:
  - 389
prosmotr:
  - 246
wpb_post_views_count:
  - 1921
dsq_thread_id:
  - 1565016797
categories:
  - Для Wordpress
tags:
  - Для Wordpress
  - оптимизация
  - плагины
---
Скорость загрузки страницы является важным фактором на сегодняшний день. Если сайт грузится долго, то пользователю будет проще закрыть вкладку и перейти на другую страницу.

Что влияет на скорость загрузки? Ответ прост и ясен &#8211; картинки, всякие js-скрипты, css, ну и конечно же сам контент, в том числе и скорость обработки самих php-файлов и выполнения запросов к БД(если речь идет о динамическом сайте).

Речь пойдет о двух вещах, о визуальных плагинах и о изображениях, так как они обычно весят больше всего остального на странице. Я вставляю как минимум одну картинку в каждый пост, поэтому приходится думать о их оптимизаций. Так вот, хочу поделиться несколькими советами, не то чтобы, что то новое, а просто самое важное на мой взгляд. Тем более, за все время существования блога, я еще не разу не писал о оптимизаций&#8230;

<!--more-->

## Изображения

**1. Выносим картинки на поддомен**

Для того чтобы браузер [параллельно](http://yuiblog.com/blog/2007/04/11/performance-research-part-4/) смог грузить и скрипты и контент и картинки, нужно вынести все это на отдельные поддомены. Например, картинки на img.site.ru, css и js на static.site.ru.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/two_parallel.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/two_parallel-300x84.png" alt="Загрузка картинок на поддомен" title="two_parallel" width="300" height="84" class="alignnone size-medium wp-image-2954" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/two_parallel-300x84.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/two_parallel.png 711w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

О том как релизовать это для WordPress без использования каких-либо дополнительных плагинов, можно прочитать на [TechTipsGeek](http://www.techtipsgeek.com/host-images-wordpress-blog-subdomain-better-speed/6897/). Или можно воспользоваться одним из этих плагинов: [CDN Tools](http://wordpress.org/extend/plugins/cdn-tools/), [WP ImageHost](http://wordpress.org/extend/plugins/wp-imagehost/) или [W3 Total Cache](http://wordpress.org/extend/plugins/w3-total-cache/)

_Я решил обойтись без плагинов и вынес картинки на img.artslab.info =)_

**2. Сжатие картинок при загрузке на сайт**

Можно в ручную сжимать каждую картинку с помощью Adobe Photoshop и функций Save for Web. А можно упростить процесс сжатия и воспользоваться плагином [WP Smush.it](http://wordpress.org/extend/plugins/wp-smushit/). При загрузке картинок плагин сразу же сжимает их и показывает насколько хорошо ему это удалось. На глаз, изменения в качестве заметны не будут, зато это позитивно повлияет на скорость загрузки. Не забудьте так же сжать изображения самой темы оформления сайта.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/smushit_pic.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/smushit_pic-300x150.jpg" alt="Сжатие картинок при загрузке" title="smushit_pic" width="300" height="150" class="alignnone size-medium wp-image-2955" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/smushit_pic-300x150.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/smushit_pic.jpg 707w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Кстати, Smush It доступен и в виде отдельного [онлайн сервиса](http://www.smushit.com/ysmush.it/).

Кроме этого, можно так же [сжимать миниатюры](http://www.skidoosh.co.uk/php/wordpress-jpeg-thumbnail-image-quality-setting-and-adjustment/). Реализуется это без плагина, просто необходимо [добавить пару строк](http://www.skidoosh.co.uk/php/wordpress-jpeg-thumbnail-image-quality-setting-and-adjustment/) в файл темы functions.php.

## Плагины

**1. Не нужно ставить 10 кнопок с разных социальных сетей**

<center>
  <img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/social_buttons.jpg" alt="Кнопки соц.сервисов" title="social_buttons" width="580" height="179" class="alignnone size-full wp-image-2963" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/social_buttons.jpg 580w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/social_buttons-300x92.jpg 300w" sizes="(max-width: 580px) 100vw, 580px" />
</center>

Я понимаю, что без кнопок социальных сетей сегодня никуда, но все таки с ними стоит быть поосторожней. Поверьте мне кнопки влияют на скорость загрузки, особенно если стоит штук 5-6, то их общий вес может оказаться вполне приличным (6 кнопок &#8211; ~100 кб). Например, кнопки Twitter, Vkonakte, Facebook подключаются в виде iframe и несут в себе много кода. Один из выходов из этого положения, вариант размещения статических кнопок, т.е. просто графики с ссылкой, без счетчика. Или поставить один виджет, например [Share](http://api.yandex.ru/share/) от Яндекса.

**2. Аккуратно выбирайте плагины визуальных украшений**

При выборе всяких слайдеров, красивых форм и прочих прелестей, смотрите на их размер и то, на какой js-библиотеке они работают. В WordPress уже используется jQuery. Поэтому я бы порекомендовал использовать плагины, который работают именно с ней, а не с другими, которые придется подгружать дополнительно (например, mootools или prototype&#8230;). Вообще в целом стоит быть осторожными с визуальными наворотами, во первых из за скорости, а во-вторых не стоит забывать о кроссбраузерности.

**3. Используйте плагин для кэширования**

Можно в ручную добавить нужные [строки в htaccess](http://www.art-shok.ru/advice/htaccess-examples/), а можно воспользоваться готовым плагином, их существует огромное количество. Из всех я бы порекомендовал [Cachify](http://wordpress.org/extend/plugins/cachify/), простой и без лишних настроек.

Вот пока вроде все, что хотел рассказать. Вообще тема оптимизаций бесконечна, на мой взгляд, в ней есть много всяких особенностей, тонкостей и нет границ.

Взлетаем 😉