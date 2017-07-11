---
id: 2482
title: 9 скриптов mp3-плееров для вставки музыки на сайт
date: 2011-05-02T02:44:32+00:00
update_date: 2016-09-05 18:40:00
dateModified: 2016-09-05 18:40:00
author: serEga
layout: post
guid: http://artslab.info/?p=2482
permalink: /skriptyi/9-skriptov-mp3-pleerov-dlya-sajta/
ljID:
  - 359
prosmotr:
  - 1396
wpb_post_views_count:
  - 6072
dsq_thread_id:
  - 1563564739
cover:
  -
categories:
  - skriptyi / CMS
tags:
  - flash
  - jquery
  - mp3 плеер
  - музыка
  - скрипт
---

Два скрипта для проигрывания музыки на сайте, я уже публиковал ранее([DewPlayer](http://artslab.info/skriptyi/dewplayer-mp3-pleer-dlya-vashego-sayta/) и [mp3 Flash Player](http://artslab.info/skriptyi/skript-mp3-pleera/)) и как оказалось, они пригодились многим. С тех пор прошло немало времени, появились новые плееры с различными возможностями. Чтобы не публиковать несколько записей, решил сразу сделать подборку с скриптов mp3-плееров, которые можно вставить на ваш сайт, либо использовать при созданий веб-приложения.


## 1. [jPlayer](http://www.jplayer.org/latest/demos/)

Миинималистичный скрипт плеера на основе HTML & CSS. Так же доступен в Flash-варианте, который будет использоваться как fallback-вариант в устаревших версиях браузера.  Доступен в разных вариантах: для аудио, видео, в комбинаций с плейлистом и без.

<center>
  <img src="https://cldup.com/lQCZRLF5XW.png" alt="jquery скрипт Mp3 плеера" title="jplayer" /><br />
  <img src="https://cldup.com/Lpq7yd1N0i.png" alt="jquery mp3 player для вставки музыки на сайт" title="jplayer2" />
</center>

## 2. [Audio.js](http://kolber.github.com/audiojs/)

<center><img src="https://cldup.com/58HjpSuyir.png" /></center>

JS-библиотека для кросс-браузерной поддержки <audio>-тега и рендеринга аудио проигрывателя. 

{% highlight html linenos %}
<audio src="/mp3/juicy.mp3" preload="auto" />
{% endhighlight %}


## 3. [Epplayer](http://www.epplayer.com/)

 Flash-плеер с плейлистом и поддержкой разных скинов.

<center>
  <img src="https://cldup.com/qaZs9J2SpN.png" alt="mp3 player script" title="epplayer" width="300" height="183"  />
</center>

## 4. [Simple Flash Mp3 Player](http://www.flabell.com/flash/Simple-Flash-Mp3-Player-37)

Легкий и минимально оформленный скрипт Mp3-проигрывателя.

<center>
  <img src="https://cldup.com/ruLhrrqjwN.png" alt="простой Mp3 плеер для сайта" title="flabell_simple_player" width="300" height="93" />
</center>


## 5. [HTML5 jQuery Audio Player](https://wordpress.org/plugins/html5-jquery-audio-player/)

Плагин плеера для WordPress. Проигрывает mp3 и ogg, работает в современных бразуерах (IE9+, Safari, Opera, Firefox, Chrome) а так же и на мобильных устроиствах. Для встраивания плеера на страницу Wordpress необходимо использовать shortcode: <pre>[hmp_player]</pre>

<center>
  <img src="https://cldup.com/MVx8kbvAAW.png" alt="плагин mp3-плеера для wordpress" title="wp_audio_player" />
</center>

**UPDATE: +2 скрипта**

## 6. [SCM Music Player](http://scmplayer.co/)

<center>
  <img src="https://cldup.com/s-d62EU-eD.png" alt="js_player" />
</center>

SCM Player - выделяется от других плееров двумя интересными функциями. Во-первых плеер предоставляет возможность переходить по страницам сайта и прослушивать при этом музыку, без всяких прерываний и перезагрузок (например, как музыка ВКонтакте). Во-вторых плеер можно прикрепить в самых верх/низ страницы, откуда будут доступны все кнопки для управления музыкой.
Кроме этого, SCM Player имеет множество настроек, несколько готовых скинов и, конечно же, поддерживает крупные плейлисты.

**Использование**

На главной странице сайта пллера находиться генератор плееера, позволяющий в несколько шагов собрать свою версию плеера. В результате сайт выдаст код, который нужно будет разместить на Вашей страничке.


## 7. [APlayer](https://aplayer.js.org/)

Простой и красивый аудио плеер на основе HTML5, поддерживает обложки и плейлисты.

<center>
<img src="https://cldup.com/r-yXD4MlfR.png" alt="aplayer красивый аудио плеер" /></center>

## 8. [React Audio Player](https://codepen.io/asommer70/pen/JGdGge)

Простой пример с плеером в виде компонента для популярного фреймворка React.

<center>
  <img src="https://cldup.com/WHfpn5IOvu.png" alt="легкий скрипт mp3 плеера в виде react компонента" />
</center>

## 9. [ngAudio](https://danielstern.github.io/ngAudio/#/)

ngAudio представялет из себя набор директив и сервисов для проигрывания аудио в рамках приложения для AngularJS.

<center>
<img src="https://cldup.com/fthKS7yrv8.png" alt="аудио директива для angular" />