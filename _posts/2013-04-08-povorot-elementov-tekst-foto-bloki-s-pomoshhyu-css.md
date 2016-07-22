---
id: 6782
title: Поворот элементов (текст, фото, блоки) средствами CSS
date: 2013-04-08T02:48:19+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=6782
permalink: /snippety/povorot-elementov-tekst-foto-bloki-s-pomoshhyu-css/
cover:
  -
wpb_post_views_count:
  - 2732
dsq_thread_id:
  - 1571820419
categories:
  - Сниппеты
tags:
  - css
  - дизайн
---
<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/povernutoe_foto.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/povernutoe_foto.jpg" alt="повернуть фото CSS" class="aligncenter size-full wp-image-6932" /></a>
</center>

С этой записью я хотел бы открыть новый раздел в моем блоге, который будет содержать различные кусочки кода, которые могут оказаться полезными при создании и оформлений сайта. Категория получит название «[Сниппеты](http://artslab.info/category/snippety/)». В будущем планирую разбить рубрику на подкатегорий для различных платформ и языков.

Начнем с CSS3.

<!--more-->

Благодаря новым возможностями появившимся в третьей версий CSS, можно легко повернуть любой объект, будь это текст, картинка или целый блок с смешанным содержанием, используя для этого всего одно свойство.

Это свойство называется transform. Рассмотрим его использование на небольшом примере с разным контентом.

Для этого поместим текст в контейнер и присвоим ему класс rotate:

**Пример с текстом:**



<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/rotate_text.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/rotate_text.jpg" alt="поворот текст css" class="aligncenter size-full wp-image-6931" /></a>
</center>



[html]<div class="rotate">Повернутый текст</div>[/html]

**Стиль CSS:**

[css].rotate {

-webkit-transform: rotate(-10deg);

-moz-transform: rotate(-10deg);

-ms-transform: rotate(-10deg);

}

[/css]

**Другие примеры:**

**Фотография:**



<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/povernutoe_foto.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/povernutoe_foto.jpg" alt="повернуть фото CSS" class="aligncenter size-full wp-image-6932" /></a>
</center>



[html]<img src="http://placeimg.com/200/200/tech" class="rotate" />[/html]

**Небольшая форма:**



<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/povernutaya_forma.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/povernutaya_forma.jpg" alt="css сниппеты" class="aligncenter size-full wp-image-6930" /></a>
</center>



[html]<div class="rotate">

<input type="text" size="20" placeholder="Логин" /><br />

<input type="password" size="20" placeholder="Пароль" /><br />

<input type="submit" size="10" />

</div>[/html]

Добавки -moz, -webkit, -ms перед свойством transform необходимы для обеспечения кроссбраузерности. -moz отвечает за корректное отображение в Mozilla Firefox, -ms для Internet Explorer, а -webkit в Google Chrome, Safari и других браузерах работающих на движке Webkit.