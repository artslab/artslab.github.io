---
id: 1242
title: Вдавленный текст с помощью CSS
date: 2011-01-21T19:28:26+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=1242
permalink: /snippety/vdavlennyj-tekst-s-pomoshhyu-css/
ljID:
  - 296
prosmotr:
  - 1683
wpb_post_views_count:
  - 3627
dsq_thread_id:
  - 1563660811
cover:
  - 
categories:
  - Сниппеты
tags:
  - css3
  - html
  - сниппет
---
<center>
  <a href="http://artslab.info/wp-content/uploads/text_shadow1.jpg"><img src="http://artslab.info/wp-content/uploads/text_shadow1.jpg" alt="текстовые эффекты с помощью css" title="text_shadow" width="587" height="179" class="alignnone size-full wp-image-1269" /></a>
</center>

Ну вот, добрались и до типографий. Небольшой пост о том, как сделать эффект вдавленного текста с помощью CSS. Реализуется очень просто, всего одной строкой.

&#8220;Вдавленность&#8221; делается с помощью одного css-свойства: text-shadow. То есть мы просто добавим подходящую по цвету тень и подвинем её так как нам нужно.

Получается вот так: 

[sourcecode language=&#8221;css&#8221;]
  
.text {
  
text-shadow: 0px 1px 0px #e5e5ee; /\* цвет должен быть темнее фона, 1px или -1px, в зависимости от цвета фона(светлый или темный) \*/
  
}
  
[/sourcecode]

Для того чтобы и в IE7 все отображалось правильно, добавим еще одну строку:

[sourcecode language=&#8221;css&#8221;]
  
.text {
  
text-shadow: 0px 1px 0px #e5e5ee;
  
filter: dropshadow(color=#e5e5ee,offX=0,offY=1);
  
}[/sourcecode]
  


Напоследок живой пример:

<div style="background: url(http://artslab.info/wp-content/uploads/bg2.jpg); width: 300px; height: 190px; display:block; margin:0 auto; color:#666;font-family:trebuchet ms;text-shadow: 0px 1px 0px #e5e5ee;">
  <div style="padding:20px 0 0 20px; font-size: 24px; ">
    ArtsLab
  </div>
  
  <p style="padding:5px 20px; font-size: 14px; text-align:justify;">
    Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum.
  </p>
</div>

<div style="cleat:both;">
</div>