---
id: 2482
title: 9 скриптов mp3-плееров для вставки музыки на сайт
date: 2011-05-02T02:44:32+00:00
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
Два скрипта для проигрывания музыки на сайте, я уже публиковал ранее([DewPlayer](http://artslab.info/skriptyi/dewplayer-mp3-pleer-dlya-vashego-sayta/) и [mp3 Flash Player](http://artslab.info/skriptyi/skript-mp3-pleera/)) и как оказалось, они пригодились многим. С тех пор прошло немало времени, появились новые разработки, поэтому решил сразу сделать небольшую подборку скриптов mp3-проигрывателей, который можно вставить на Ваш сайт.

## 1. [niftyPlayer](http://www.varal.org/media/niftyplayer/)

Главное преимущество скрипта, это его легкость &#8211; всего 4 кб.

<center>
  <img src="{{site.img_cdn}}/nifty_player.jpg" alt="легкий скрипт mp3 плеера" title="nifty_player" width="182" height="59" class="alignnone size-full wp-image-2483" />
</center>



**Использование плеера**

Для того чтобы встроить плеер на нужную страницу, необходимо воспользоваться этим кодом:

{% highlight html %}

<object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,0,0" width="165" height="38" id="niftyPlayer1" align="">

<param name=movie value="niftyplayer.swf?file=betty.mp3&as=1">

<param name=quality value=high>

<param name=bgcolor value=#FFFFFF>

<embed src="niftyplayer.swf?file=betty.mp3&as=1" quality=high bgcolor=#FFFFFF width="165" height="38" name="niftyPlayer1" align="" type="application/x-shockwave-flash" pluginspage="http://www.macromedia.com/go/getflashplayer">

</embed>

</object>

{% endhighlight %}

_file=betty.mp3 &#8211; это, соответственно, путь и название проигрываемого файла._

_as=1 &#8211; этот параметр отвечает за autostart_

_Кроме того, можно легко настроить внешний вид плеера, изменив соответствующий цвета в коде._

И конечно нужно не забыть подключить js-файл с плеером.

{% highlight html %}

<script type="text/javascript" language="javascript" src="niftyplayer.js"></script>

{% endhighlight %}

Более подробную инструкцию и документаций можно найти на официальном сайте NiftyPlayer.

## 2. [Flash Mp3 Player](http://www.flashmp3player.org/)

Более крупный вариант плеера &#8211; из преимуществ стоит отметить наличие плейлиста и настройки цвета внешнего вида.

<center>
  <a href="{{site.img_cdn}}/free_falsh_mp3_player.jpg"><img src="{{site.img_cdn}}/free_falsh_mp3_player-300x117.jpg" alt="бесплатный flash mp3 плеер для вставки на сайт" title="free_falsh_mp3_player" width="300" height="117" class="alignnone size-medium wp-image-2485" /></a>
</center>

## 3. [jPlayer](http://www.jplayer.org/0.2.1/demos/)

Доступен в разных вариант, как с плейлистом, так и без.

<center>
  <a href="{{site.img_cdn}}/jplayer.jpg"><img src="{{site.img_cdn}}/jplayer-300x280.jpg" alt="jquery скрипт Mp3 плеера" title="jplayer" width="300" height="280" class="alignnone size-medium wp-image-2486" srcset="{{site.img_cdn}}/jplayer-300x280.jpg 300w, {{site.img_cdn}}/jplayer.jpg 429w" sizes="(max-width: 300px) 100vw, 300px" /></a><a href="{{site.img_cdn}}/jplayer2.jpg"><img src="{{site.img_cdn}}/jplayer2-300x75.jpg" alt="jquery mp3 player для вставки музыки на сайт" title="jplayer2" width="300" height="75" class="alignnone size-medium wp-image-2487" srcset="{{site.img_cdn}}/jplayer2-300x75.jpg 300w, {{site.img_cdn}}/jplayer2.jpg 432w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

## 4. [Audio.js](http://kolber.github.com/audiojs/)

Главный плюс это легкость интеграция плеера на страницу. В Header страницы прикрепляется js, а сам плеер вставляется с помощью кода, такого вида:

[sourcecode language=&#8221;html&#8221;]<audio src="/mp3/juicy.mp3" preload="auto" />[/sourcecode]



<center>
  <a href="{{site.img_cdn}}/audiojs.jpg"><img src="{{site.img_cdn}}/audiojs-300x73.jpg" alt="jquery html5 mp3 player" title="audiojs" width="300" height="73" class="alignnone size-medium wp-image-2488" srcset="{{site.img_cdn}}/audiojs-300x73.jpg 300w, {{site.img_cdn}}/audiojs.jpg 548w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

## 5. [Yahoo mp3 Playe](http://developer.yahoo.com/mediaplayer/)r

Симпатичный плеер от Yahoo

<center>
  <a href="{{site.img_cdn}}/yahoo_player.gif"><img src="{{site.img_cdn}}/yahoo_player-300x47.gif" alt="скрипт Mp3 плеера от yahoo" title="yahoo_player" width="300" height="47" class="alignnone size-medium wp-image-2491" srcset="{{site.img_cdn}}/yahoo_player-300x47.gif 300w, {{site.img_cdn}}/yahoo_player.gif 540w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

## 6. [Epplayer](http://www.epplayer.com/)

Плеер с плейлистом и поддержкой разных скинов.

<center>
  <a href="{{site.img_cdn}}/epplayer.jpg"><img src="{{site.img_cdn}}/epplayer-300x183.jpg" alt="mp3 player script" title="epplayer" width="300" height="183" class="alignnone size-medium wp-image-2492" srcset="{{site.img_cdn}}/epplayer-300x183.jpg 300w, {{site.img_cdn}}/epplayer.jpg 431w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

## 7. [Simple Flash Mp3 Player](http://www.flabell.com/flash/Simple-Flash-Mp3-Player-37)

Легкий и минимально оформленный скрипт Mp3-проигрывателя.

<center>
  <a href="{{site.img_cdn}}/flabell_simple_player.jpg"><img src="{{site.img_cdn}}/flabell_simple_player-300x93.jpg" alt="простой Mp3 плеер для сайта" title="flabell_simple_player" width="300" height="93" class="alignnone size-medium wp-image-2493" srcset="{{site.img_cdn}}/flabell_simple_player-300x93.jpg 300w, {{site.img_cdn}}/flabell_simple_player.jpg 330w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

## 8. [Flash Mp3 Player](http://www.flabell.com/flash/Flash-Mp3-Player-29)

Навороченный скрипт от Flabell. Тут и плеилист и выбор артиста, описание альбома и другие фишки.

<center>
  <a href="{{site.img_cdn}}/flabell_flash_player.jpg"><img src="{{site.img_cdn}}/flabell_flash_player-300x162.jpg" alt="многофункциональный скрипт Mp3-плеера для вставки на сайт" title="flabell_flash_player" width="300" height="162" class="alignnone size-medium wp-image-2494" srcset="{{site.img_cdn}}/flabell_flash_player-300x162.jpg 300w, {{site.img_cdn}}/flabell_flash_player.jpg 566w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

## 9. [WordPress Audio Player](http://wpaudioplayer.com/)

Доступен в виде самостоятельного плеера, а так же в виде плагина для WordPress.

<center>
  <img src="{{site.img_cdn}}/wp_audio_player.jpg" alt="плагин mp3-плеера для wordpress" title="wp_audio_player" width="311" height="42" class="alignnone size-full wp-image-2495" srcset="{{site.img_cdn}}/wp_audio_player.jpg 311w, {{site.img_cdn}}/wp_audio_player-300x40.jpg 300w" sizes="(max-width: 311px) 100vw, 311px" />
</center>

**UPDATE: +2 скрипта**

### 10. <a href="http://scmplayer.net/" target="_blank">SCM Music Player</a>

<center>
  <a href="{{site.img_cdn}}/js_player.png"><img src="{{site.img_cdn}}/js_player-300x124.png" alt="js_player" class="aligncenter size-medium wp-image-7368" srcset="{{site.img_cdn}}/js_player-300x124.png 300w, {{site.img_cdn}}/js_player.png 668w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

SCM Player &#8211; выделяется от других плееров двумя главными функциями. Во-первых плеер предоставляет возможность переходить по страницам сайта и прослушивать при этом музыку, без всяких прерываний и перезагрузок (например, как музыка ВКонтакте). Во-вторых плеер можно прикрепить в самых верх/низ страницы, откуда будут доступны все кнопки для управления музыкой.
Кроме этого, SCM Player имеет множество настроек, несколько готовых скинов и, конечно же, поддерживает крупные плейлисты.

<center>
  <a href="{{site.img_cdn}}/pleer_kak_vk.png"><img src="{{site.img_cdn}}/pleer_kak_vk-300x107.png" alt="scm player js" class="aligncenter size-medium wp-image-7370" srcset="{{site.img_cdn}}/pleer_kak_vk-300x107.png 300w, {{site.img_cdn}}/pleer_kak_vk-1024x368.png 1024w, {{site.img_cdn}}/pleer_kak_vk.png 1059w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



**Использование**

На главной странице сайта пллера находиться генератор позволяющий в несколько шагов собрать плеер и выдать код, который нужно будет разместить на сайте. так же, на страничке есть полноценная инструкция для более конкретного знакомства с плеером.

### 11. <a href="http://www.codebasehero.com/2011/06/html-music-player/" target="_blank">ttwMusicPlayer</a>

<center>
  <a href="{{site.img_cdn}}/player_dlya_saita.png"><img src="{{site.img_cdn}}/player_dlya_saita-235x300.png" alt="музыкальный плеер js" class="aligncenter size-medium wp-image-7366" srcset="{{site.img_cdn}}/player_dlya_saita-235x300.png 235w, {{site.img_cdn}}/player_dlya_saita.png 423w" sizes="(max-width: 235px) 100vw, 235px" /></a>
</center>

Красивый плеер на основе HTML5 & JavaScript. Пример с использованием, доступен на страничке плеера.