---
id: 6346
title: Стеклянная/прозрачная кнопка с помощью CSS3
date: 2013-03-04T16:28:47+00:00
update_date: 2016-10-05 18:40:00
author: serEga
layout: post
guid: http://artslab.info/?p=6346
permalink: /stati/steklyannayaprozrachnaya-knopka-s-pomoshhyu-css3/
cover:
  - 6358
dsq_thread_id:
  - 1565017960
categories:
  - stati
tags:
  - css3
  - html
  - кнопка
  - эффекты
---
Возможности CSS3 открывают огромный ряд новых возможностей перед веб-дизайнерами. Сегодня я хотел бы поделиться с вами один из примеров, где используются несколько интересных свойств для создания прозрачной (стеклянной) кнопки с различными тенями. Результат выглядит примерно так:

<center>
  <img src="{{site.img_cdn}}/css3_prozrachnaya_knopka.jpg" alt="стеклянная кнопка на css3" title="css3_prozrachnaya_knopka" width="497" height="232" class="aligncenter size-full wp-image-6349" srcset="{{site.img_cdn}}/css3_prozrachnaya_knopka.jpg 497w, {{site.img_cdn}}/css3_prozrachnaya_knopka-300x140.jpg 300w" sizes="(max-width: 497px) 100vw, 497px" />
</center>

Создадим div-контейнер с ссылкой в html-файле, которая и станет нашей кнопкой. Для этого присвоим ей какой-нибудь CSS-класс, например, button:

{% highlight html linenos %}
<div id="container">
  <a href="#" class="button">Click Me</a>
</div>
{% endhighlight %}

Теперь перейдем к оформленияю класса button в CSS. Самое интересное и главное свойство для создания всех теней на кнопке, это &#8211; **box-shadow**. Лучше всего, попробуйте сами поэкспериментировать с параметрами этого свойства, изменяя цвета и значения. Условные добавки &#8220;-moz&#8221; (Firefox) и &#8220;-webkit&#8221; (Chrome) в двух других классах, служат для точного указания движков разных браузеров.

**border-radius** - служит для указания радиуса закругления углов на кнопке.

И наконец **opacity**, свойство которое позволит установить значение для прозрачности всего блока (кнопки). Я добавил его к селектору :hover, т.е. при наведении курсора кнопка будет становиться тусклее.

Вот и весь код стиля с нашей кнопкой:

{% highlight css linenos %}
  a.button {
    font-family: Helvetica, arial, serif;
    color:#fff;
    text-align:center;
    font-size:30px;
    cursor: pointer;
    text-decoration: none;
    padding:10px;
    border: 1px solid rgba(0,0,0,0.5);
    border-bottom: 3px solid rgba(0,0,0,0.5);
    border-radius: 3px;
    -moz-border-radius: 3px;
    -webkit-border-radius: 3px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.5), /* Exterior Shadow */
      inset 0 1px rgba(255,255,255,0.3), /* Top light Line */
      inset 0 10px rgba(255,255,255,0.2), /* Top Light Shadow */
      inset 0 10px 20px rgba(255,255,255,0.25), /* Sides Light Shadow */
      inset 0 -15px 30px rgba(0,0,0,0.3); /* Dark Background */
    -webkit-box-shadow: 0 2px 8px rgba(0,0,0,0.5),
      inset 0 1px rgba(255,255,255,0.3),
      inset 0 10px rgba(255,255,255,0.2),
      inset 0 10px 20px rgba(255,255,255,0.25),
      inset 0 -15px 30px rgba(0,0,0,0.3);
    -moz-box-shadow: 0 2px 8px rgba(0,0,0,0.5),
      inset 0 1px rgba(255,255,255,0.3),
      inset 0 10px rgba(255,255,255,0.2),
      inset 0 10px 20px rgba(255,255,255,0.25),
      inset 0 -15px 30px rgba(0,0,0,0.3);
  }

  a.button:hover {
    opacity: 0.7;
    filter: alpha(opacity=70);
    -moz-opacity:0.7;
    -khtml-opacity: 0.7;
  }

{% endhighlight %}

<center>
  <a href="{{site.img_cdn}}/transparent_btn_css3.jpg"><img src="{{site.img_cdn}}/transparent_btn_css3-300x216.jpg" alt="стеклянная кнопка с помощью css3" title="transparent_btn_css3" width="300" height="216" class="aligncenter size-medium wp-image-6355" srcset="{{site.img_cdn}}/transparent_btn_css3-300x216.jpg 300w, {{site.img_cdn}}/transparent_btn_css3.jpg 761w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

# Демо:

<p data-height="231" data-theme-id="414" data-slug-hash="qaoOVK" data-default-tab="result" data-user="4gray" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/4gray/pen/qaoOVK/">Transparent buttons with CSS</a> by 4gray (<a href="http://codepen.io/4gray">@4gray</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>
