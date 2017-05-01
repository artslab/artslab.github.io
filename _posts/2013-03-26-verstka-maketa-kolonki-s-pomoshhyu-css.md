---
id: 6763
title: 'Верстка макета: колонки с помощью CSS'
date: 2013-03-26T17:17:37+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=6763
permalink: /snippety/verstka-maketa-kolonki-s-pomoshhyu-css/
cover:
  -
wpb_post_views_count:
  - 787
dsq_thread_id:
  - 1569027697
categories:
  - snippety
tags:
  - css
---
При необходимости размещения текста на сайте в несколько колонок, можно воспользоваться следующим CSS-кодом.

<div style="padding: 1em;-moz-column-count: 3;-moz-column-gap: 1em;-webkit-column-count: 3;-webkit-column-gap: 1em;column-count: 3;column-gap: 1em; width: 90%; border:1px solid #ccc; background:#eee;">
  Ut varius volutpat facilisis. Integer magna ligula, malesuada vel commodo eu, tincidunt sed odio. Curabitur ut purus et arcu vestibulum adipiscing quis non quam. Nam velit purus, dapibus ut rhoncus nec, bibendum sed risus. Donec egestas, enim eget venenatis dictum, dolor quam scelerisque ipsum, et vulputate est mi dictum nisi.
</div>

<!--more-->



{% highlight css %}

.three-column {
	padding: 1em;
	-moz-column-count: 3;
	-moz-column-gap: 1em;
	-webkit-column-count: 3;
	-webkit-column-gap: 1em;
	column-count: 3;
	column-gap: 1em;
}

{% endhighlight %}

Несколько слов о двух главных свойстах:

* column-count &#8211; отвечает за количество столбцов.

* column-gap &#8211; отвечает за размер отступа между отдельными столбцами.

Добавки -moz и -webkit у свойств необходимы для обеспечения кроссбраузерности. -moz, соответственно, для Firefox, а -webkit для браузеров на основе движка WebKit, например Google Chrome.