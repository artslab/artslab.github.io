---
id: 6368
title: Добавляем свои ссылки на панель навигаций WordPress
date: 2013-08-22T21:19:04+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=6368
permalink: /snippety/dobavlyaem-svoi-ssylki-na-panel-navigacij-wordpress/
cover:
  -
wpb_post_views_count:
  - 723
dsq_thread_id:
  - 1629795060
categories:
  - snippety
tags:
  - wordpress
  - сниппет
---
Продолжу делиться полезными сниппетами для WordPress. Данный код позволит Вам добавить любую ссылку в верхнюю навигационную панель WP, видимую только для администратора блога. Код необходимо добавить в файл темы functions.php.

Например, я добавил на панель ссылку для быстрой очистки кэша, которая была запрятано далеко в настройках плагина.

<center>
  <a href="{{site.img_cdn}}/dabavit_ssilku_v_navbar.png"><img src="{{site.img_cdn}}/dabavit_ssilku_v_navbar-300x47.png" alt="добавить ссылку в NavBar WP" class="aligncenter size-medium wp-image-7509" srcset="{{site.img_cdn}}/dabavit_ssilku_v_navbar-300x47.png 300w, {{site.img_cdn}}/dabavit_ssilku_v_navbar.png 789w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

### Код функций:

{% highlight php %}

function add\_blog\_menu()

{

global $wp\_admin\_bar;

if (!is\_super\_admin() || !is\_admin\_bar_showing())

return;

if (is_admin())

{

$wp\_admin\_bar->add_menu(array(

&#8216;id&#8217; => &#8216;blog&#8217;,

&#8216;title&#8217; => &#8216;Заголовок ссылки&#8217;, //текст ссылки

&#8216;href&#8217; => site_url() . &#8216;/url&#8217; //ссылка

)

);

}

}

add\_action(&#8216;wp\_before\_admin\_bar\_render&#8217;, &#8216;add\_blog_menu&#8217;);

{% endhighlight %}

(<a href="http://validwebs.com/423/add-blog-link-to-admin-nav/" target="_blank">via</a>)