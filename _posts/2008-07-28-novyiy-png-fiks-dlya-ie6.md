---
id: 361
title: Новый PNG фикс для IE6
date: 2008-07-28T16:36:23+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=361
permalink: /sovetyi/novyiy-png-fiks-dlya-ie6/
ljID:
  - 211
prosmotr:
  - 17526
wpb_post_views_count:
  - 6190
dsq_thread_id:
  - 1565020948
cover:
  -
categories:
  - sovetyi
tags:
  - fix
  - js
  - png
---
<center>
  <a href="{{site.img_cdn}}/png_fix_for_internet_explorer.jpg"><img src="{{site.img_cdn}}/png_fix_for_internet_explorer.jpg" alt="" title="png_fix_for_internet_explorer" width="292" height="273" class="alignnone size-full wp-image-832" /></a>
</center>



Всем нам известно что наш _&#8220;любимый&#8221;_ Internet Explorer 5 и 6 (до 7 версий) не поддерживает прозрачность формата PNG и что с этим как-то нужно бороться. Так как бывают случаи, когда gif со своими 256 цветами просто не подходит. Ранее я уже публиковал на сайте <a href="http://artslab.info/?p=58#comments" target="_blank">один фикс</a>, который решает эту проблему, но он был не совсем идеален. Например, не отображалась прозрачность со свойством background-image.

Поэтому я предлагаю воспользоваться другим, новым фиксом от [Unit Interactive Labs](http://labs.unitinteractive.com/index.php), размер которого занимает менее 2 kb.

Установка данного решения довольно таки проста, нужно всего лишь <a href="http://labs.unitinteractive.com/unitpngfix.php" target="_blank">скачать</a> сам js-фикс, загрузить его к себе на сервер и прописать его в header на нужных страничках:

<pre lang="html">&lt;!--[if lt IE 7]&gt;
&lt;script type="text/javascript" src="unitpngfix.js"&gt;&lt;/script&gt;
&lt;![endif]--&gt;</pre>

Источник: <a href="http://stylizedweb.com/2008/07/27/a-brand-new-png-fix-for-ie6/" target="_blank">StylizedWeb.com</a>