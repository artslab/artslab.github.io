---
id: 5864
title: Подсветка ключевых слов в результатах поиска WordPress (без плагина)
date: 2013-09-06T00:31:01+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=5864
permalink: /snippety/podsvetka-klyuchevyx-slov-v-rezultatax-poiska-wordpress-bez-plagina/
cover:
  - 7841
wpb_post_views_count:
  - 1213
dsq_thread_id:
  - 1719789169
categories:
  - snippety
tags:
  - Для Wordpress
  - сниппет
---
Данный сниппет позволит выделить поисковую фразу в результатах поиска по сайта без использования каких-либо дополнительных WordPress-плагинов. Пример на скриншоте:

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/podsvetka_poiskovoi_frazi.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/podsvetka_poiskovoi_frazi-300x136.png" alt="подсветка результата" class="aligncenter size-medium wp-image-7840" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/podsvetka_poiskovoi_frazi-300x136.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/podsvetka_poiskovoi_frazi.png 723w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>



<!--more-->

Нижепреведенный код с 2 функциями необходимо добавить в файл functions.php:

{% highlight php %}

function search\_excerpt\_highlight() {
	$excerpt = get\_the\_excerpt();
	$keys = implode(&#8216;|&#8217;, explode(&#8216; &#8216;, get\_search\_query()));
	$excerpt = preg_replace(&#8216;/(&#8216; . $keys .&#8217;)/iu&#8217;, &#8216;<strong class="search-highlight">&#92;&#48;</strong>&#8217;, $excerpt);
	echo &#8216;<p>&#8217; . $excerpt . &#8216;</p>&#8217;;
}

function search\_title\_highlight() {
	$title = get\_the\_title();
	$keys = implode(&#8216;|&#8217;, explode(&#8216; &#8216;, get\_search\_query()));
	$title = preg_replace(&#8216;/(&#8216; . $keys .&#8217;)/iu&#8217;, &#8216;<strong class="search-highlight">&#92;&#48;</strong>&#8217;, $title);
	echo $title;
}

{% endhighlight %}

Теперь перейдем в файл search.php отвечающий за отображение результатов поиска. В нем необходимо заменить 2 стандартные функций на наши новые функций, которые мы только что переписали. the\_title() на search\_title\_highlight() и the\_excerpt(), соответственно на search\_excerpt\_highlight().

В style.css можно добавить класс для того чтобы выделить найденную фразу с помощью фона:

{% highlight css %}

.search-highlight {
	background:#FFFFB6;
}

{% endhighlight %}

<a href="http://wordpress.stackexchange.com/questions/16070/how-to-highlight-search-terms-without-plugin" target="_blank">Источник</a>