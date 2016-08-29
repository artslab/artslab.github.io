---
id: 5118
title: Эффект Tilt-Shift с помощью CSS3 и jQuery
date: 2012-09-07T16:32:33+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=5118
permalink: /skriptyi/effekt-tilt-shift-s-pomoshhyu-css3-i-jquery/
prosmotr:
  - 68
cover:
  - 6421
wpb_post_views_count:
  - 1842
dsq_thread_id:
  - 1565021050
categories:
  - skriptyi / CMS
tags:
  - css3
  - jquery
  - tilt-shift
  - скрипт
---
<center>
  <a href="{{site.img_cdn}}/tilt_shift_with_css3.png"><img class="aligncenter size-medium wp-image-5133" title="tilt_shift_with_css3" src="{{site.img_cdn}}/tilt_shift_with_css3-300x147.png" alt="эффект tilt-shift" width="300" height="147" srcset="{{site.img_cdn}}/tilt_shift_with_css3-300x147.png 300w, {{site.img_cdn}}/tilt_shift_with_css3.png 889w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>Если Вы время от времени читаете мой блог, то должны быть знакомы с

[эффектом Tilt-Shift](http://artslab.info/kreativnyie-rabotyi/timelapse-tilt-shift-dva-effekta-v-odnom-video/ "Timelapse + Tilt-Shift — два эффекта в одном видео"), про который я уже неоднократно писал. Если же нет, тогда рекомендую заглянуть в пост с [уроком Photoshop (текст и видео)](http://artslab.info/uroki-photoshop/effekt-tilt-shift-v-photoshop-urok/ "Эффект Tilt-Shift в Photoshop (урок)") или посмотреть [красивый видеоролик](http://artslab.info/kreativnyie-rabotyi/timelapse-tilt-shift-dva-effekta-v-odnom-video/) на эту тему .

Сегодня я хотел бы рассказать о возможности использования этого эффекта на сайте без графического редактора, а только с помощью кода. Для этого нам понадобиться библиотека jQuery, браузер с поддержкой CSS3 и скрипт [tiltShift.js](https://github.com/noeltock/tiltShift.js). Пример и использование в продолжений записи.

<!--more-->

### Пример

[<img class="aligncenter size-medium wp-image-5136" title="tilt_shift_s_css3" src="{{site.img_cdn}}/tilt_shift_s_css3-300x199.png" alt="эффект тайл шифт без фотошопа" width="300" height="199" srcset="{{site.img_cdn}}/tilt_shift_s_css3-300x199.png 300w, {{site.img_cdn}}/tilt_shift_s_css3.png 614w" sizes="(max-width: 300px) 100vw, 300px" />]({{site.img_cdn}}/tilt_shift_s_css3.png)

Живой пример работы скрипта можно увидеть на [этой страничке](http://www.noeltock.com/tilt-shift-css3-jquery-plugin/).

### Использование

Прикручиваем css и js в шапке страницы:

[sourcecode language=&#8221;html&#8221;]

<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>

<script type="text/javascript" src="jquery.tiltShift.js"></script>

<script type="text/javascript"> <![CDATA[

jQuery(document).ready(function() {

$(&#8216;.tiltshift&#8217;).tiltShift();

});

]]></script>

[/sourcecode]

Вставляем саму картинку и прописываем к ней специальные атрибуты и параметрами, с которыми можно смело экспериментировать (радиус размытия, позиция, размытие по вертикали/горизонтали)

[sourcecode language=&#8221;html&#8221;]

<img class="tiltshift" src="url" alt="" data-position="50" data-blur="2" data-focus="10" data-falloff="10" data-direction="y" />

[/sourcecode]

На этом и все, пробуйте, экспериментируйте. Приятного Вам дня 🙂