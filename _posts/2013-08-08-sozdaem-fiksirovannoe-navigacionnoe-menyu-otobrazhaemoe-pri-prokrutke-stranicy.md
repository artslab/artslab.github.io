---
id: 7373
title: Создаем фиксированное навигационное меню, отображаемое при прокрутке страницы
date: 2013-08-08T22:44:05+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7373
permalink: /snippety/sozdaem-fiksirovannoe-navigacionnoe-menyu-otobrazhaemoe-pri-prokrutke-stranicy/
cover:
  -
wpb_post_views_count:
  - 3302
dsq_thread_id:
  - 1585960807
categories:
  - snippety
tags:
  - css
  - html
  - js
---
Сегодня небольшой пост с примером, в котором мы создадим фиксированное навигационное меню, которое будет появляться в шапке сайта при прокрутке страницы вниз. Демо доступно для просмотра в песочнице на <a href="http://codepen.io/4gray/full/hrIan" target="_blank">Codepen</a>, там же можно и поэкспериментировать с кодом.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/fiksirovanoe_menu.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/fiksirovanoe_menu-300x269.jpg" alt="fiksirovanoe_menu" class="aligncenter size-medium wp-image-7376" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/fiksirovanoe_menu-300x269.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/fiksirovanoe_menu.jpg 833w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

1. Для начала создадим простенькую структуру странички. Разместим здесь наше меню, заголовок/название сайта и добавим немного контента в виде Lorem ipsum&#8217;а для возможности прокрутки.

**Код:**

{% highlight html %}

<ul id="menu">
	<li><a href="#">HOME</a></li>
	<li><a href="#">FAQ</a></li>
	<li><a href="#">ABOUT</a></li>
	<li><a href="#">CONTACT</a></li>
	<li><a href="#">RSS</a></li>
</ul>

<h2>Заголовок сайта</h2>

<div id="content">

<h3>Прокрути страницу вниз</h3>

<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

<img src="http://placeimg.com/500/500/tech" />

&#8230;

</div>

{% endhighlight %}

2. Создадим несколько CSS-классов для чтобы приукрасить страницу и выделить наше меню.

**Код:**

{% highlight css %}

body {
	padding:0;
	margin:0;
	font: 14px Helvetica;
}

#content {
	width:500px;
	margin: 0 auto;
}

a {
	color: #5366e1;
	text-decoration: none;
}

a:hover {
	color: #6189e1;
}

#menu {
	padding: 20px 0;
	text-align: center;
	margin: 0;
	width: 100%;
}

#menu ul {
	padding: 0;
	margin:0;
}

#menu li {
	display: inline;
	list-style: none;
	padding: 10px;
}

h2 {
	font-size: 24px;
	color: #333;
	text-align: center;
	margin: 0;
	padding: 25px;
	background: #ccc;
}

.fixed a {
	color: #fff;
	text-decoration: none;
}

.fixed li:hover {
	background: #666;
}

{% endhighlight %}

И самое главном добавим класс fixed, который будет добавлять к нашему меню в js-файле при прокрутке страницы вниз и, соответственно, удаляться при обратной прокрутке в самый верх.

**Код:**

{% highlight css %}

.fixed {
	position: fixed;
	z-index: 10;
	background: #444;
	top: 0;
}

{% endhighlight %}

3. Теперь займемся частью с javascript кодом, в которой мы будем показывать и скрывать наше меню, используя для этого созданный нами класс fixed.

**Код:**

{% highlight javascript %}

	$(function () {

	$(window).scroll(function(event) {
		if($(this).scrollTop() > 150) {
			$("#menu").fadeIn();
			$("#menu").addClass(&#8216;fixed&#8217;)
		}

		else {
			$("#menu").removeClass(&#8216;fixed&#8217;)
		}

	});

});

{% endhighlight %}

**$(this).scrollTop() > 150** &#8211; обозначает, что наше меню будет появляться после того, как пользователь прокрутит страницу на более чем 150 пикселей вниз.

С помощью jQuery-функций addClass() мы добавляем необходимый класс к элементу с меню и removeClass(), соответственно, удаляет класс.

Пример можно посмотреть на <a href="http://codepen.io/4gray/full/hrIan" target="_blank">Codepen</a>, там же можно и поэкспериментировать с кодом.