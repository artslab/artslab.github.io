---
id: 6437
title: 'Пасхальное яйцо &#8220;Harlem Shake&#8221; для вашего блога на WordPress'
date: 2013-03-11T15:08:03+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=6437
permalink: /stati/pasxalnoe-yajco-harlem-shake-dlya-vashego-bloga-na-wordpress/
cover:
  -
wpb_post_views_count:
  - 2338
dsq_thread_id:
  - 1565020159
categories:
  - stati
tags:
  - js
  - php
  - Для Wordpress
---
Несмотря на понедельник, предлагаю заняться бестолковым делом 🙂

Если на YouTube ввести фразу &#8220;do the harlem shake&#8221; и нажать Enter, то можно увидеть пляску элементов под уже поднадоевшую мелодию из трендового видео-безумства. Окончательную идею реализовать что-то подобное для своего сайта, мне подкинул один из посетителей, который вбил эту фразу в поисковую строку на моем блоге (увидел через плагин [Search Meter](http://artslab.info/news/30-plaginov-dlya-wordpress-kotorye-ispolzuyutsya-v-etom-bloge/)). Можете попробовать [поискать](http://artslab.info/?s=do+the+harlem+shake), а под катом реализация.

[<img src="{{site.img_cdn}}/harlem_shake_dlya_saita.jpg" alt="harlem shake для сайта" class="aligncenter size-medium" width="347" width="79" />]({{site.img_cdn}}/harlem_shake_dlya_saita.jpg)

<!--more-->

Приступим.

1. Во-первых, нужно найти js-скрипт и мелодию. Воспользуемся скриптом с сайта [HSKmaker](http://hsmaker.com/), который за нас уже [успели вытащить](http://time2hack.com/2013/02/create-your-own-websites-harlem-shake-meme.html) из кода страницы.

{% highlight html %}<script src="http://files.time2hack.com/time2hack.harlem.shake.min.js" type="text/javascript"></script>

<div style=" height:0px; width:0px; overflow:hidden;">

<audio controls="controls" autoplay="autoplay" loop="loop">

<source src="http://files.time2hack.com/time2hack.harlem.shake.ogg" type="audio/ogg" />

</audio>

<script type="text/javascript">

ready(function () {

harlemShake();

});

</script>

</div>{% endhighlight %}

2. Теперь нам нужно чтобы WordPress реагировал на фразу &#8220;do the harlem shake&#8221; или какое-либо другое слово, это уж на ваше усмотрение.

Для этого откроем файл темы с отображением результатов поиска, обычно это search.php. Находим в коде:

{% highlight php %}<?php if (have_posts()) : ?>{% endhighlight %}

И перед этим фрагментом вставляем код с Harlem Shake:

{% highlight php %}

<?php if($_GET[&#8216;s&#8217;] == &#8216;do the harlem shake&#8217;) { ?>

<script src="http://files.time2hack.com/time2hack.harlem.shake.min.js" type="text/javascript"></script>

<div style=" height:0px; width:0px; overflow:hidden;">

<audio controls="controls" autoplay="autoplay" loop="loop">

<source src="http://files.time2hack.com/time2hack.harlem.shake.ogg" type="audio/ogg" />

</audio>

<script type="text/javascript">

ready(function () {

harlemShake();

});

</script>

</div>

<?php } ?>

{% endhighlight %}

3. При необходимости очищаем кэш и проверяем 🙂

Как видите, создать &#8220;пасхальное яйцо&#8221; для WP-поиска очень даже просто.

<center>
  <a href="{{site.img_cdn}}/shaker.jpg"><img src="{{site.img_cdn}}/shaker-300x204.jpg" alt="harlem shake для сайта" class="aligncenter size-medium wp-image-6441" srcset="{{site.img_cdn}}/shaker-300x204.jpg 300w, {{site.img_cdn}}/shaker-1024x698.jpg 1024w, {{site.img_cdn}}/shaker.jpg 1091w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>