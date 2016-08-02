---
id: 1322
title: Добавляем отображение фавиконок в блогролл
date: 2011-01-26T17:18:22+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=1322
permalink: /wordpress/dobavlyaem-otobrazhenie-favikonok-v-blogroll/
ljID:
  - 301
prosmotr:
  - 45
wpb_post_views_count:
  - 795
dsq_thread_id:
  - 1632158566
categories:
  - Для Wordpress
tags:
  - favicon
  - plugin
  - Для Wordpress
---
<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/blogroll_with_favicons1.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/blogroll_with_favicons1.jpg" alt="блогролл с фавиконкам" title="blogroll_with_favicons" width="295" height="262" class="alignnone size-full wp-image-1337" /></a>
</center>

Немного приукрасил свой блогролл, добавил к сайтам их фавиконки. Вроде мелочь, зато приятно.

Сделать такой блогролл довольно таки просто, для этого существует плагин для WordPress &mdash; [Faviroll](http://wordpress.org/extend/plugins/faviroll/). Устанавливаем его, выставляем права 775 на папку cache, которая находится вместе с плагином. Затем заходим в настройки **Faviroll** и сохраняем их. В этот момент фавиконки сайтов, которые были в вашем блогролле, сохранятся в папку cache и после этого появятся на сайте.

PS: Небольшой совет для тех кто использует статический список ссылок. Чтобы не копаться на каждом сайте и искать иконки, можно взять их с яндекса, например вот так:

[sourcecode language=&#8221;html&#8221;]

<li style="background: url('http://favicon.yandex.net/favicon/artslab.info') no-repeat;list-style: none;padding-left: 23px;">
  Текст тут
</li>
<!-- соответственно место artslab.info, указываем нужный сайт -->



[/sourcecode]

_Выглядит это так:_

<li style="background: url('http://favicon.yandex.net/favicon/artslab.info') no-repeat;list-style: none;padding-left: 23px;">
  Артслаб.инфо
</li>