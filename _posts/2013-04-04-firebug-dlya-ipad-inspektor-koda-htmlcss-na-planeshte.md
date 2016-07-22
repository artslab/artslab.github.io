---
id: 6880
title: 'Firebug для iPad &#8211; инспектор кода (HTML&#038;CSS) на планеште'
date: 2013-04-04T14:56:41+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=6880
permalink: /prilozheniya-dlya-ipod-touchiphone/firebug-dlya-ipad-inspektor-koda-htmlcss-na-planeshte/
cover:
  -
wpb_post_views_count:
  - 2330
dsq_thread_id:
  - 1574126492
categories:
  - Приложения для iPod Touch/iPhone
tags:
  - css
  - html
  - ipad
  - iphone
---
<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/firebug_ipad_css_html.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/firebug_ipad_css_html-300x225.jpg" alt="исходный код ipad" class="aligncenter size-medium wp-image-6881" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/firebug_ipad_css_html-300x225.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/firebug_ipad_css_html.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Небольшой букмарклет для владельцев iOS-устройств, который открывает внизу экрана окно с инспектором кода Firebug. Конечно, использовать такой инструмент на планшете, мягко говоря, не совсем удобно. Для теста и отладки мобильной версий сайта, лучше найти подходящий симулятор мобильных устройств для обычного компьютера. Тем не менее букмарклет полностью работоспособен. Можно легко посмотреть исходный код страницы и редактировать HTML и CSS-код, не устанавливая дополнительного приложения.

<!--more-->

Установка:

1. Открываем Safari и добавляем любую закладку, даем ей имя Firebug. Сохраняем.

2. Копируем код букмарклета с Firebug:

[js]

javascript:(function(F,i,r,e,b,u,g,L,I,T,E){if(F.getElementById(b))return;E=F\[i+&#8217;NS&#8217;]&&F.documentElement.namespaceURI;E=E?F[i+&#8217;NS&#8217;\](E,&#8217;script&#8217;):F\[i\](&#8216;script&#8217;);E\[r\](&#8216;id&#8217;,b);E\[r\](&#8216;src&#8217;,I+g+T);E\[r\](b,u);(F\[e\](&#8216;head&#8217;)\[0]||F[e\](&#8216;body&#8217;)\[0]).appendChild(E);E=new%20Image;E[r\](&#8216;src&#8217;,I+L);})(document,&#8217;createElement&#8217;,&#8217;setAttribute&#8217;,&#8217;getElementsByTagName&#8217;,&#8217;FirebugLite&#8217;,&#8217;4&#8242;,&#8217;firebug-lite.js&#8217;,&#8217;releases/lite/latest/skin/xp/sprite.png&#8217;,&#8217;https://getfirebug.com/&#8217;,&#8217;#startOpened&#8217;);

[/js]

3. Редактируем добавленную закладку и место старого URL вставляем скопированный код.

4. Пробуем. Откройте любой сайт и нажмите по закладке.

([Источник](http://www.jamesmacfie.com/2012/03/debug-your-html-css-on-the-ipadiphone/))