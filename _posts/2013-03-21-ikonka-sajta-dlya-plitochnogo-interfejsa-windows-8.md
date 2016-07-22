---
id: 6651
title: Иконка сайта для плиточного интерфейса Windows 8
date: 2013-03-21T19:34:54+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=6651
permalink: /stati/ikonka-sajta-dlya-plitochnogo-interfejsa-windows-8/
cover:
  - 6670
wpb_post_views_count:
  - 2418
dsq_thread_id:
  - 1563695449
categories:
  - Статьи
tags:
  - windows 8
  - иконка
---
<center>
  <img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/ikonka_saita_dlya_windows8.png" alt="иконка сайта в modern ui" class="aligncenter size-medium wp-image-6667" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/ikonka_saita_dlya_windows8.png 450w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/ikonka_saita_dlya_windows8-300x166.png 300w" sizes="(max-width: 450px) 100vw, 450px" />
</center>

Новое плиточное меню (Modern UI) в Windows 8 позволяет прикреплять ссылки на сайты в виде отдельных плиток. Если прикрепить сайт, то по умолчанию отобразиться растянутая фавиконка с стандартным серым фоном. Выглядит не очень красиво (пример на скриншоте), но это легко можно исправить. Нужно добавить специальный мета-код на ваш сайт и указать в нем иконку, заголовок и цвет самой плитки.

<!--more-->

Размер иконки должен составлять 144x144px, лучше всего сохранить ее в формате png с прозрачным фоном. Такой же размер требуется и для iOS-девайсов ([иконка для домашнего экрана](http://artslab.info/stati/optimizaciya_saita_dlya_iphone_ipad_ipod/ "Оптимизация сайта для для Iphone/iPod/iPad (добавляем иконку и сообщение приветствия)")), но тем не менее, я не рекомендую использовать одно и то же изображения для разных устройств.

На мой взгляд, в случае с Modern UI лучше всего смотрятся монохромные иконки, поэтому я бы не стал делать что-то слишком красочное.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/11.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/11-300x168.jpg" alt="интерфейс metro в windows 8" class="aligncenter size-medium wp-image-3920" /></a>
</center>

Всего нам понадобиться добавить три строки в шапку сайта, т.е. между тегами <head> и </head>. За фоновый цвет плитки отвечает первый метатег, второй содержит путь к необходимой иконке, а в третьем указан заголовок страницы, который будет отображаться на плитке под иконкой.

{% highlight html %}

<meta name="msapplication-TileColor" content="#302f30"/>
<meta name="msapplication-TileImage" content="http://artslab.info/tile_icon.png"/>
<meta name="application-name" content="ArtsLab"/>

{% endhighlight %}

Напоследок, поделюсь сервисом <a href="http://www.buildmypinnedsite.com/" target="_blank">BuildMyPinnedSite</a>, он поможет с предпросмотром при оформлений, а так же умеет генерировать вышеуказанный код.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/windows_8_ikonka.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/windows_8_ikonka-300x215.jpg" alt="сервис buildmypinnedsite" class="aligncenter size-medium wp-image-6671" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/windows_8_ikonka-300x215.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/windows_8_ikonka.jpg 996w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>