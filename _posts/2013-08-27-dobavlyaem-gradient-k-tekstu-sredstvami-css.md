---
id: 7596
title: Добавляем градиент к тексту средствами CSS
date: 2013-08-27T00:08:17+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7596
permalink: /snippety/dobavlyaem-gradient-k-tekstu-sredstvami-css/
cover:
  -
wpb_post_views_count:
  - 830
dsq_thread_id:
  - 1651100324
categories:
  - snippety
tags:
  - css
  - сниппет
---
Еще один CSS-сниппет, который позволит добавить градиент на любой текст, без использования какой-либо графики.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/text_s_gradientom.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/text_s_gradientom-300x67.png" alt="текст с градиентом css" class="aligncenter size-medium wp-image-7597" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/text_s_gradientom-300x67.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/text_s_gradientom.png 519w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

Думаю код не нуждается ни в каких дополнительных комментариях. Вот и сам класс:

{% highlight css %}

.text {
	background: -webkit-linear-gradient(#f1c40f, #c0392b);
	-webkit-background-clip: text;
	-webkit-text-fill-color: transparent;
}

{% endhighlight %}

Пример, как всегда, доступен на <a href="http://codepen.io/4gray/pen/sxGka" target="_blank">Codepen</a>.

<p data-height="268" data-theme-id="414" data-slug-hash="sxGka" data-user="4gray" data-default-tab="result" class='codepen'>
  See the Pen <a href='http://codepen.io/4gray/pen/sxGka'>CSS3 Text Gradient</a> by 4gray (<a href='http://codepen.io/4gray'>@4gray</a>) on <a href='http://codepen.io'>CodePen</a>
</p>