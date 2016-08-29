---
id: 7324
title: Эффект 3D-текста с помощью CSS3
date: 2013-08-06T01:04:05+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7324
permalink: /snippety/effekt-3d-teksta-s-pomoshhyu-css3/
cover:
  -
wpb_post_views_count:
  - 2320
dsq_thread_id:
  - 1574029045
categories:
  - snippety
tags:
  - css
  - эффекты
---
3D-эффект для создания объемного текста можно легко создать с помощью Photoshop, Gimp или любого другого графического редактора, но а так же и с помощью CSS3, без использования дополнительной графики. Преимуществом любого эффекта с применением CSS3 является быстрая скорость загрузки, а главным недостатком, конечно же, кроссбраузерность.

<center>
  <a href="{{site.img_cdn}}/sozdat_3dtext_s_css.png"><img src="{{site.img_cdn}}/sozdat_3dtext_s_css.png" alt="эффект 3d текста на css" class="aligncenter size-medium wp-image-7329" srcset="{{site.img_cdn}}/sozdat_3dtext_s_css.png 653w, {{site.img_cdn}}/sozdat_3dtext_s_css-300x74.png 300w" sizes="(max-width: 653px) 100vw, 653px" /></a>
</center>

Далее сниппет с небольшим примером.

<!--more-->

Для начала создадим обычный div-контейнер с классом &#8220;effect&#8221; и поместим в него наш текст:

{% highlight html %}

<div class="effect">3D-текст с помощью CSS3</div>

{% endhighlight %}

Добавим CSS-стиль к нашему классу:

{% highlight css %}

.effect {
	font:normal 60px Arial;
	color:#FFFFFF;
	text-shadow: 0 1px 0 #ccc,
	0 2px 0 #c9c9c9,
	0 3px 0 #bbb,
	0 4px 0 #b9b9b9,
	0 5px 0 #aaa,
	0 6px 1px rgba(0,0,0,.1),
	0 0 5px rgba(0,0,0,.1),
	0 1px 3px rgba(0,0,0,.3),
	0 3px 5px rgba(0,0,0,.2),
	0 5px 10px rgba(0,0,0,.25),
	0 10px 10px rgba(0,0,0,.2),
	0 20px 20px rgba(0,0,0,.15);
}

{% endhighlight %}

Пример:

<div class="effect-text">
  3D-Текст с помощью CSS
</div>


Поиграть с примером кода можно на [Codepen](http://codepen.io/4gray/pen/Iotuf)

[via](http://www.cssrex.com/tips-tricks/how-to-create-3d-text-using-css3/)