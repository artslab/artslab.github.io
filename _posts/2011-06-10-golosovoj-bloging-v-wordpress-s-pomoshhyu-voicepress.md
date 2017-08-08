---
id: 3286
title: Голосовой блогинг в WordPress с помощью VoicePress
date: 2011-06-10T13:32:33+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=3286
permalink: /wordpress/golosovoj-bloging-v-wordpress-s-pomoshhyu-voicepress/
ljID:
  - 411
prosmotr:
  - 86
wpb_post_views_count:
  - 817
dsq_thread_id:
  - 1565022116
categories:
  - wordpress
tags:
  - google chrome
  - wordpress
  - плагин
---
[Голосовой поиск](http://artslab.info/wordpress/golosovoj-poisk-na-sajte/), теперь блогинг с помощью голоса, что-то я зачастил на эту тему? Все потому, что как мне кажется у всего этого есть будущее. Лень &#8211; двигатель прогресса, если судить именно так, то наличие полного голосового управления компьютером, в скором, нам не избежать. Конечно, не факт что все этим будут пользоваться, но вполне имеет место быть, даже просто как хорошая альтернатива.

Перейдем к главному, написание поста с помощью голоса. Для этого, естественно, понадобится микрофон, Chrome и четкое выговаривание слов и целых предложений. [Google Chrome](http://artslab.info/tag/google-chrome/) придется использовать, так как реализовано это, все на том же Google Speech API.

<center>
  <a href="{{site.img_cdn}}/voicepress.jpg"><img src="{{site.img_cdn}}/voicepress-300x161.jpg" alt="голосовой блогинг" title="voicepress" width="300" height="161" class="alignnone size-medium wp-image-3311" /></a>
</center>

В случае с поиском мы добавляли [несколько строк](http://artslab.info/wordpress/golosovoj-poisk-na-sajte/) к input, для того чтобы в поле появилась иконка с микрофоном и возможность распознования речи. Следующий шаг, в принципе, был очевиден. Почему бы не прикрутить тоже самое к текстовому полю textarea и выпустить это в виде отдельного плагина, неапример для WordPress. Это и представляет из себя дополнение [VoicePress.it](http://voicepress.it/).

_[Источник](http://wpcandy.com/previewed/voicepress-speech-recognition-plugin)_<!--more-->
