---
id: 7889
title: Эффект черно-белого фото (CSS)
date: 2013-09-09T13:09:07+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7889
permalink: /snippety/effekt-cherno-belogo-foto-css/
cover:
  -
wpb_post_views_count:
  - 2922
dsq_thread_id:
  - 1744091295
categories:
  - Сниппеты
tags:
  - css
  - сниппет
  - фото
---
Возможности CSS3 легко позволяют превратить цветную фотографию в черно-белую, используя для этого всего несколько строк кода. Добавим еще один эффект для обратного перехода при наведении на изображение и можно смело использовать код для каких-нибудь превью-миниатюр на сайтах.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/cherno-beloe-foto-css.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/cherno-beloe-foto-css-300x101.png" alt="черно-белое фото css" class="aligncenter size-medium wp-image-7890" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/cherno-beloe-foto-css-300x101.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/cherno-beloe-foto-css.png 609w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

Код:

{% highlight css %}

.bw {
	filter: url(&#8220;data:image/svg+xml;utf8,<svg xmlns=\'http://www.w3.org/2000/svg\'><filter id=\'grayscale\'><feColorMatrix type=\'matrix\' values=\'0.3333 0.3333 0.3333 0 0 0.3333 0.3333 0.3333 0 0 0.3333 0.3333 0.3333 0 0 0 0 0 1 0\'/></filter></svg>#grayscale&#8221;); /\* Firefox 10+, Firefox on Android \*/
	filter: gray; /\* IE6-9 \*/
	-webkit-filter: grayscale(1); /\* Google Chrome, Safari 6+ & Opera 15+ \*/
	-moz-filter: grayscale(100%);
	-ms-filter: grayscale(100%);
	-o-filter: grayscale(100%);
	filter: grayscale(100%);
}

.bw:hover {
	filter: none;
	-webkit-filter: grayscale(0);
}

{% endhighlight %}

Демо:

<p data-height="268" data-theme-id="414" data-slug-hash="EidBl" data-user="4gray" data-default-tab="result" class='codepen'>
  See the Pen <a href='http://codepen.io/4gray/pen/EidBl'>Grayscale Image with CSS</a> by 4gray (<a href='http://codepen.io/4gray'>@4gray</a>) on <a href='http://codepen.io'>CodePen</a>
</p>