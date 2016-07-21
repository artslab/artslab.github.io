---
id: 58
title: Прозрачность png в Internet Explorer 6
date: 2007-08-11T02:53:21+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=58
permalink: /sovetyi/prozrachnost-png-v-internet-explorer-6/
ljID:
  - 48
prosmotr:
  - 1016
wpb_post_views_count:
  - 3084
dsq_thread_id:
  - 1565021335
categories:
  - Советы
tags:
  - internet explorer
  - png
  - прозрачность пнг
---
<p STYLE="text-align: center">
  <img WIDTH="238" HEIGHT="215" BORDER="0" ALT="internet explorer png fix" TITLE="internet explorer png fix" SRC="http://artslab.info/wp-content/uploads/png_fix_for_ie.jpg" />
</p>

Наверное каждый веб-мастер уже знаком с проблемой **отображения прозрачности картинок формата .png** в **internet explorer 6**. Да наш &#8220;любимый&#8221; IE 6 версий (в 7 все отлично) не хочет корректно отображать прозрачные картинки этого формата т.е. вообще никакой прозрачности не наблюдается.Что делать? Я встречал много разных <a rel="none" TARGET="_blank" TITLE="прозрачность png в ie 6" HREF="http://www.google.de/search?hl=de&q=%D0%9F%D1%80%D0%BE%D0%B7%D1%80%D0%B0%D1%87%D0%BD%D0%BE%D1%81%D1%82%D1%8C+png+%D0%B2+Internet+Explorer&btnG=Google-Suche&meta=">способов решения</a> этой проблемы, но этот показался мне самым **простым**.

<!--more-->

1. Качаем этот **<a TARGET="_blank" TITLE="download pngfix for ie" HREF="http://www.box.net/shared/xmbox4g45h" rel="none">файлик</a>** (javascript)

2. Достаем с архива и кладем его в корневую папку вместе с index.html (index.php)
  
3. В index.html (index.php) добавляем между <head> </head> следующий код:

> <!&#8211;[if lt IE 6.]&#8211;>
  
> <script defer type=&#8221;text/javascript&#8221; src=&#8221;pngfix.js&#8221; mce_src=&#8221;pngfix.js&#8221;></script>
  
> <!&#8211;[endif]&#8211;>

Собственно и все! Теперь все картинки **везде** будут отображаться корректно.

_Источник: <a rel="none" TARGET="_blank" TITLE="источник" HREF="http://www.xyberneticos.com/index.php/2007/06/08/solucionar-las-transparencias-de-imagenes-png-en-internet-explorer/">xyberneticos</a>_