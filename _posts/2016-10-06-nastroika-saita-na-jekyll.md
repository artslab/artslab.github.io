---
id: 3127562
title: Настройка блога на основе Jekyll
author: serEga
layout: post
permalink: /jekyll/nastroika-saita-na-jekyll/
categories:
  - jekyll
tags:
  - jekyll
amp: true
date: 2016-10-06 01:22:00
---

В этой записи я собрал несколько разных тем касающихся первоначальной настройки блога на [Jekyll](http://jekyllrb.com). Этот пост будет интересен тем людям, которые как и я, впервые только недавно познакомились с Jekyll. В этом посте мы займёмся локализацей дат, выведем похожие записи для постов и рассмотрим основные плагины поддерживаемые на Github Pages.

## Локализация дат
Одной из необходимых первоначальных настроек является перевод дат для их отображения в привычном нам формате, а так же месяцев на русском языке.

1. В папке **_includes/** создадим отдельный шаблон для форматирования даты в нужном нам формате, я назову файл **date.html**:

	{% highlight html linenos %}
	{% raw %}
	{% assign m = include.date | date: "%-m" %}
	{{ include.date | date: "%-d" }}
	{% case m %}
	  {% when '1' %}января
	  {% when '2' %}февраля
	  {% when '3' %}марта
	  {% when '4' %}апреля
	  {% when '5' %}мая
	  {% when '6' %}июня
	  {% when '7' %}июля
	  {% when '8' %}августа
	  {% when '9' %}сентября
	  {% when '10' %}октября
	  {% when '11' %}ноября
	  {% when '12' %}декабря
	{% endcase %}
	{{ include.date | date: "%Y" }}
	{% endraw %}
	{% endhighlight %}

2. Вставляем наш шаблон с помощью тега **include** в нужное место и передаем ему переменную с датой, которая будет отформатирована, так как указано в нашем шаблоне:

	```
	{% include date.html date=page.date %}
    ```

## Вывод похожих записей
Вывести список похожих/интересных записей (Similar Posts) монжо с помощью данного сниппета:

{% highlight html linenos %}
{% raw %}
{% assign hasSimilar = '' %}
 {% for post in site.related_posts %}
     {% assign postHasSimilar = false %}
     {% for tag in post.tags %}
         {% for thisTag in page.tags %}
             {% if postHasSimilar == false and hasSimilar.size < 6 and post != page and tag == thisTag %}
                 {% if hasSimilar.size == 0 %}
                 <h4>Похожие записи</h4>
                 <ul>
                 {% endif %}
                 <li class="relatedPost">
                     <a href="{{ site.url }}{{ post.url }}">{{ post.title }}
                     {% if post.series %}
                         (Series: {{ post.series }})
                     {% endif %}
                     </a>
                 </li>
                 {% capture hasSimilar %}{{ hasSimilar }}*{% endcapture %}
                 {% assign postHasSimilar = true %}
             {% endif %}
         {% endfor %}
     {% endfor %}
 {% endfor %}
 {% if hasSimilar.size > 0 %}
    </ul>
{% endif %}
{% endraw %}
{% endhighlight %}

via [gist](https://gist.github.com/Ovilia/ea95e762544d84f00281)

## SEO-плагин
Github Pages имеет поддержку плагина Jekyll-SEO-Tag. Для того чтобы использовать его на сайте, в первую очередь необходимо прописать его в Gemfile, а так же вставить [liquid](https://github.com/Shopify/liquid)-тег {% seo %} в head:

{% highlight html linenos %}
{% raw %}
<head>
    {% seo %}
</head>
{% endraw %}
{% endhighlight %}

Плагин поддерживает несколько переменных - title, description, image, author, которые можно объявить в [Front Matter](https://jekyllrb.com/docs/frontmatter/) для каждого отдельного поста. Более подробно о возможностях Jekyll-SEO-Tag можно почитать на [страничке плагина](https://github.com/jekyll/jekyll-seo-tag).

## Поддерживаемые плагины
В сети можно встретить большое количество различных плагинов для Jekyll, но к сожалению Github Pages поддерживает только ряд "стандартных" плагинов. Например, таких как: jekyll-sitemap, jekyll-feed, jekyll-paginate, jekyll-seo-tag, jekyll-gist  и другие ([полный список поддерживаемых плагинов](https://pages.github.com/versions/)). В случае, если вы хотите использовать дополнительные плагины, то необходимо будет сгенерировать сайт локально и затем загрузить его в репозиторий вместе с папкой **_site**, которая и содержит сгенерированный контент.

## Ускорение генераций сайта локально
При большом количестве записей генерация сайта занимает приличное время и минутные ожидания после каждого изменения в коде являются очень утомительным. Например, для тестирования дизайна и функционала сайта не нужно загружать все записи блога. Для того чтобы ускорить процесс и ограничить количество генерированного контента можно воспользоваться дополнительной опцией **--limit-posts NUMBER**. Полноценная команда для запуска Jekyll с ограничением в **две записи** выглядит так:

```
bundle exec jekyll serve --incremental --limit_posts 2
``

PS: Запись будет пополняться и другими полезными сниппетами. Буду рад комментариям с полезными советами или вопросами :-)
