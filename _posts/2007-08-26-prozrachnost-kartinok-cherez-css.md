---
id: 103
title: Прозрачность картинок через CSS
date: 2007-08-26T00:40:55+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=103
permalink: /stati/prozrachnost-kartinok-cherez-css/
ljID:
  - 79
prosmotr:
  - 124
cover:
  -
wpb_post_views_count:
  - 1388
dsq_thread_id:
  - 1565022304
categories:
  - stati
tags:
  - css
  - html
  - opacity
  - прозрачность
  - эффекты
---
<p style="text-align: center">
  <a href="#"><img src="http://artslab.info/wp-content/uploads/banner.jpg" alt="artslab header" border="0" /></a>
</p>

В одном из <a href="http://artslab.info/?p=100#comments" title="комментарий" target="_blank">комментариев</a> на сайте спрашивали о там как создать **эффект**_ вроде того что на картинке выше. То есть чтобы при наведении на картинку, ее **прозрачность** становилась 100%-ной, а на неактивной картинке поменьше (50%), чтобы она выглядела потусклее. Далее следует небольшое описание, как это сделать.

<!--more-->



1. Добавляем в <span style="font-weight: bold">style.css</span> следующий код:

{% highlight css %}a.opacity img {

filter:alpha(opacity=50);

-moz-opacity: 0.5;

opacity: 0.5;}

a.opacity:hover img {

filter:alpha(opacity=100);

-moz-opacity: 1.0;

opacity: 1.0;

}

{% endhighlight %}

2. Подключаем style.css к главной странице **index.html**/php. Добавляем между <head> и </head>

{% highlight html %} <link rel="stylesheet" href="style.css" type="text/css" media="screen" />{% endhighlight %}

3. Вставляем на главной(index.hml):

{% highlight html %}

<a href="#" class="opacity">

<img src="logo.jpg" alt="Image" />

</a>

{% endhighlight %}

На этом и все, **пример** можно скачать <a href="http://www.box.net/shared/atqkpz8rrg" title="download example" target="_blank">отсюда</a>.