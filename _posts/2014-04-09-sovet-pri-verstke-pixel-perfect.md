---
id: 8146
title: Совет при верстке Pixel Perfect
date: 2014-04-09T18:06:14+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=8146
permalink: /snippety/sovet-pri-verstke-pixel-perfect/
cover:
  - 7291
wpb_post_views_count:
  - 1298
dsq_thread_id:
  - 2649851058
categories:
  - snippety
tags:
  - psd
  - сниппет
---
В веб-дизайне существует понятие верстки пиксель-в-пиксель (pixel perfect) &#8211; это когда требуется точная верстка сайта из макета psd.

Хотел бы поделиться одним замечательным сниппетом найденным на [DesignerNews](https://news.layervault.com/comments/53577).

<pre>.element {
    background: url("/images/about.png") no-repeat scroll 0 0 transparent;
    height: 1010px;
    left: 0;
    opacity: 0.5;
    position: absolute;
    top: 0;
    width: 1280px;
    z-index: 9999;
}</pre>

Суть заключается в том, что мы накладываем наш PSD-макет поверх веб-элементов и таким образом, имеем возможность верстать под макетом и сверять результат HTML-разметки с PSD-макетом.

Такой подход экономит нервы и постоянные переключения окон 🙂