---
id: 7859
title: Создаем размытый текст (CSS)
date: 2013-09-08T20:46:12+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7859
permalink: /snippety/sozdaem-razmytyj-tekst-css/
cover:
  -
wpb_post_views_count:
  - 1603
dsq_thread_id:
  - 1734149169
categories:
  - snippety
tags:
  - css
  - сниппет
---
Очередной CSS сниппет позволяющий создать размытый текст (blurry text). Добавим немного анимаций при наведении на текст для того чтобы размытый текст плавно переходил в четкую типографию.

<center>
  <img src="https://cldup.com/s_N7qSNHKO.png" alt="размытие текста на css" class="aligncenter size-medium" />
</center>

<!--more-->

Код:

{% highlight css %}

	h2 {
		color: transparent;
		text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
		font-size: 62px;
		-webkit-transition: text-shadow 2.0 ease-out;
		-moz-transition: text-shadow 2.0 ease-out;
		-ms-transition: text-shadow 2.0 ease-out;
		-o-transition: text-shadow 2.0 ease-out;
		transition: text-shadow 2.0 ease-out;
	}

	h2:hover {
		text-shadow: 0 0 0 rgba(0, 0, 0, 1);
		-webkit-transition: text-shadow 0.5s;
		-moz-transition: text-shadow 0.5s;
		-ms-transition: text-shadow 0.5s;
		-o-transition: text-shadow 0.5s;
		transition: text-shadow 0.5s;
		cursor: default;
	}

{% endhighlight %}

Демо:

<p data-height="300" data-theme-id="414" data-slug-hash="gBAsk" data-default-tab="css,result" data-user="4gray" data-embed-version="2" data-pen-title="Blurry Text" class="codepen">See the Pen <a href="https://codepen.io/4gray/pen/gBAsk/">Blurry Text</a> by 4gray (<a href="https://codepen.io/4gray">@4gray</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>