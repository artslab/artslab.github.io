---
id: 7910
title: Создаем простые часы для сайта с помощью JavaScript
date: 2013-09-11T13:33:42+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7910
permalink: /snippety/sozdaem-prostye-chasy-dlya-sajta-s-pomoshhyu-javascript/
cover:
  -
wpb_post_views_count:
  - 2222
dsq_thread_id:
  - 1748088489
categories:
  - Сниппеты
tags:
  - js
  - сниппет
  - часы
---
Сегодня предлагаю небольшой сниппет, который позволит вам добавить простые часы на сайт, используя для этого немного JavaScript-кода. Пример можно увидеть на <a href="http://codepen.io/4gray/pen/prytd" target="_blank">Codepen</a>.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/chasi_dlya_saita.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/chasi_dlya_saita-300x81.png" alt="часы для сайта на яваскрипт" class="aligncenter size-medium wp-image-7911" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/chasi_dlya_saita-300x81.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/chasi_dlya_saita.png 680w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

### HTML:

{% highlight html %}

<div id="clock"></div>

{% endhighlight %}

Подготовим контейнер в котором будут отображаться чаи и присвоим ему id.

### JS:

{% highlight javascript %}

setInterval(function(){
	var date = new Date();

	var format = [
		(date.getHours()),
		(date.getMinutes()),
		(date.getSeconds())
	].join(":");

	document.getElementById("clock").innerHTML = format;
}, 900);

{% endhighlight %}

Код довольно-таки прост. Главное это создание класса Date и получение текущего времени с помощью трех функций getHours(), getMinutes и getSeconds(). И в конце вывод времени в зависимости от установленного интервала (900) в элемент с соответствующим id (#clock).

### Демо в песочнице:

<p data-height="268" data-theme-id="414" data-slug-hash="prytd" data-user="4gray" data-default-tab="result" class='codepen'>
  See the Pen <a href='http://codepen.io/4gray/pen/prytd'>Clock</a> by 4gray (<a href='http://codepen.io/4gray'>@4gray</a>) on <a href='http://codepen.io'>CodePen</a>
</p>