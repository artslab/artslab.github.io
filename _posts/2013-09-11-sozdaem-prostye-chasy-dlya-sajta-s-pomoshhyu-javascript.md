---
id: 7910
title: Создаем простые часы для сайта с помощью JavaScript
date: 2013-09-11 13:33:42 +0000
author: serEga
layout: post
guid: http://artslab.info/?p=7910
permalink: "/snippety/sozdaem-prostye-chasy-dlya-sajta-s-pomoshhyu-javascript/"
cover:
- 
wpb_post_views_count:
- 2222
dsq_thread_id:
- 1748088489
categories:
- snippety
tags:
- js
- сниппет
- часы

---
Сегодня предлагаю небольшой сниппет, который позволит вам добавить простые часы на сайт, используя для этого немного JavaScript-кода. Пример можно увидеть на <a href="http://codepen.io/4gray/pen/prytd" target="_blank">Codepen</a>.

<center>
<img src="{{site.baseurl}}/forestryio/images/chasi_dlya_saita.png" />
</center>

### HTML:

{% highlight html %}

<div id="clock"></div>

{% endhighlight %}

Подготовим контейнер в котором будут отображаться часы и присвоим ему id.

### JS:

{% highlight javascript %}
    setInterval(function(){  
    	const date = new Date();  
        const format = [      
        	(date.getHours()),      
        	(date.getMinutes()<10?'0':'') + date.getMinutes(),      
        	(date.getSeconds())  ].join(":");  
        document.getElementById("clock").innerHTML = format;
    }, 900);
{% endhighlight %}

Код довольно-таки прост. Главное это создание класса Date и получение текущего времени с помощью трех функций getHours(), getMinutes() и getSeconds(). И в конце вывод времени в зависимости от установленного интервала (900) в элемент с соответствующим id (#clock).

### Демо в песочнице:

<p data-height="300" data-theme-id="414" data-slug-hash="prytd" data-default-tab="js,result" data-user="4gray" data-pen-title="Clock" class="codepen">See the Pen <a href="https://codepen.io/4gray/pen/prytd/">Clock</a> by 4gray (<a href="https://codepen.io/4gray">@4gray</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>