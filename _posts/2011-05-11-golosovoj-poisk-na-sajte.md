---
id: 2652
title: Добавляем голосовой поиск на сайт
date: 2011-05-11T01:10:11+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=2652
permalink: /wordpress/golosovoj-poisk-na-sajte/
ljID:
  - 369
prosmotr:
  - 763
wpb_post_views_count:
  - 2998
cover:
  -
dsq_thread_id:
  - 1565024080
categories:
  - Все для Google Chrome
  - Для Wordpress
tags:
  - google chrome
  - Для Wordpress
  - поиск
  - скрипт
  - сниппет
---
Перед там как начать, стоит сразу отметить, что голосовой поиск работает только в последних версиях Google Chrome, поэтому этот пост нужно отнести в категорию &#8220;будущее где-то здесь&#8221; =)

Попробовать голосовой поиск можно у меня в блоге, для этого достаточно нажать по иконке микрофона в поисковой строке, сверху.

<center>
  <img src="{{site.img_cdn}}/golosovoi_poisk_google_chrome.jpg" alt="добавить голосовой поиск на сайт" title="golosovoi_poisk_google_chrome" width="322" height="137" class="alignnone size-full wp-image-2654" />
</center>

Меня удивило насколько просто и легко встраивается данный функционал на сайт. Думал нужно будет загружать какие-то js-библиотеки, css-файлы с картинками, нет, ничего. Для работы голосового поиска используется &#8220;x-webkit-speech&#8221; и все необходимое уже встроено в движке браузера (Webkit).

Поэтому нужно дописать всего пару параметров в строку поиска `<input.. />`

Перейдем к главному. Не важно, на каком движке сделан Ваш сайт, главное чтобы присутствовала функция поиска =). Рассмотрим на примере моего блога на WordPress.

Находим код поисковой формы, в теме моего блога, я вынес его в файл header.php и searchform.php. Код:

[sourcecode language=&#8221;html&#8221;]

<form method="get" id="searchform" action="http://artslab.info/">

<input type="text" value="Поиск на сайте" name="s" id="s" onblur="if (this.value == &#8221;)

{this.value = &#8216;Поиск на сайте&#8217;;}" onfocus="if (this.value == &#8216;Поиск на сайте&#8217;)

{this.value = &#8221;;}">

<input type="hidden" id="searchsubmit">

</form>

[/sourcecode]

Чтобы добавить голосовой поиск, необходимо дописать в <input /> следующее:

[sourcecode language=&#8221;html&#8221;]x-webkit-speech="" speech="" onwebkitspeechchange="this.form.submit();"[/sourcecode]

В целом получается так:

[sourcecode language=&#8221;html&#8221;]<form method="get" id="searchform" action="http://artslab.info/">

<input type="text" value="Поиск на сайте" name="s" id="s" onblur="if (this.value == &#8221;)

{this.value = &#8216;Поиск на сайте&#8217;;}" onfocus="if (this.value == &#8216;Поиск на сайте&#8217;)

{this.value = &#8221;;}" x-webkit-speech="" speech="" onwebkitspeechchange="this.form.submit();">

<input type="hidden" id="searchsubmit">

</form>[/sourcecode]

Экспериментируем =)

_PS: Интересно работает ли это на андроидфонах, у самого нет возможности проверить&#8230;_