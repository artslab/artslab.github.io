---
id: 4170
title: Решение проблемы с синхронизацией iPhone/iPad в Windows 8 DP
date: 2011-12-27T23:54:46+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=4170
permalink: /windows-8-2/reshenie-problemy-s-sinxronizaciej-iphoneipad-v-windows-8-dp/
prosmotr:
  - 127
wpb_post_views_count:
  - 2100
dsq_thread_id:
  - 1565020153
categories:
  - Windows 8
tags:
  - ios
  - ipad
  - iphone
  - windows 8
---
<img src="{{site.img_cdn}}/windows8_iphone_sync_itunes_problem.jpg" alt="синхронизация iphone в windows 8" title="windows8_iphone_sync_itunes_problem" width="290" height="150" class="aligncenter size-full wp-image-4171" />

При синхронизаций iPhone через iTunes в Windows 8 Developer Preview у меня появилась проблема. Программа просто-напросто отказывается находить подключенный девайс. Погуглив, я нашел решение на одном [англоязычном форуме](http://www.eightforums.com/hardware-drivers/2375-trouble-iphone-4-driver-windows-8-a-2.html), которое помогло мне синхронизировать телефон. Перед каждой синхронизацией приходиться проделывать несколько простых действий.

Цитирую с форума:

<p class="twitter-message">
  1) Close iTunes<br /> 2) Go to services<br /> 3) Stop &#8220;Apple Mobile Device&#8221;<br /> 4) Plug device in, wait for the 1/2 chimes<br /> 5) Start &#8220;Apple Mobile Device&#8221;<br /> 6) Open iTunes<br /> 7) During Sync you might get an &#8220;Unable to receive data from sync services&#8221;, but it still syncs
</p>