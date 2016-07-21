---
id: 564
title: Разрешаем редактирование комментариев юзерам (WP)
date: 2010-06-21T16:56:44+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=564
permalink: /wordpress/razreshaem-redaktirovanie-kommentariev-yuzeram-wp/
ljID:
  - 265
prosmotr:
  - 66
wpb_post_views_count:
  - 1444
dsq_thread_id:
  - 1565015963
categories:
  - Для Wordpress
tags:
  - Для Wordpress
  - плагин
---
<center>
  <img src="http://s.wordpress.org/extend/plugins/editable-comments/screenshot-2.png?r=255430" alt="editable comments for wordpress users" width="382" height="197" />
</center>


  
Хотел бы поделиться с вами плагином <a href="http://wordpress.org/extend/plugins/editable-comments/" target="_blank">Editable Comments</a> для WordPress, с помощью которого пользователь, который оставил комментарий, сможет отредактировать его за выставленное в настройках время после публикаций. Установить дополнение можно прямо из админ-панели вордпресса.
  
Перед активацией плагина будет необходимо разместить ссылку редактирования в шаблоне, для этого необходимо добавить одну строку кода.
  
Открываем comments.php и находим там:
  
[sourcecode language=&#8217;php&#8217;]<?php comment_text() ?>[/sourcecode]


  
и после этого добавляем:
  
[sourcecode language=&#8217;php&#8217;]<?php if ( class_exists( 'WPEditableComments' ) ) { WPEditableComments::link('Modify'); } ?>[/sourcecode]

Теперь активируем плагин и переходим в его настройки в админ-панели, там требуется указать только интервал времени в минутах.
  


<center>
  <img src="http://s.wordpress.org/extend/plugins/editable-comments/screenshot-1.png?r=255485" alt="редактирование комментариев в wordpress" />
</center>