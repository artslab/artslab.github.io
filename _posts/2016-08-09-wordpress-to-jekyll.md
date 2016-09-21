---
id: 3127562
title: Переезд с Wordpress на Jekyll
author: serEga
layout: post
permalink: /jekyll/wordpress-to-jekyll/
categories:
  - jekyll
tags:
  - jekyll
amp: true
---

Медлительность и громоздкость Wordpress в последнее время стала разочаровывать меня все больше и больше. От части это было связанно с большим количеством активированных плагинов и непотимизированной темой. Но при всем этом, сама CMS с новыми версиями становится только объемнее, а большинство из новшест не являются необходимыми для обычного блога. Окончание баланса на хостинге дало еще один дополрнительный толчок для переезда. После Wordpress’а хотелось чего-то простенького и быстрого, выбор пал на Jekyll. Jekyll - это генератор статических сайтов, который отлично дружит с Github Pages. А это значит, что используя Github Pages мы получаем халявный хостинг к которому можем прикрутить наш домен.

<p align="center">
<amp-img src="http://i.imgur.com/qWUDmfI.png" alt="генератор статических сайтов jekyll" width="498" height="230" layout="responsive"></amp-img></p>

Процесс написания поста теперь является таковым:

1. Создаем новый *.md файл и открываем его в любимом редакторе
2. Пишем пост используя разметку markdown
3. Делаем push файла с постом в наш репозиторий на github
4. Ждем пару минуток пока генерируется новый пост

Теперь коротко о главном при переезде:

1. **Экпорт контента:** Экспортировать записи и посты из Wordpress помог плагин [Jekyll Exporter](https://wordpress.org/plugins/jekyll-exporter/). Плагин так же экспортирует изображения из папки wp-content. Но так как в моем случае они хранились на отдельном поддомене img.artslab.info, то пришлось скачать их вручную.
2. **Хостинг контента:** Как я уже упомянул выше, Jekyll отлично работает на Github Pages, поэтому теперь весь контент лежит в отдельном репозиторий и хостинг обходится бесплатно.
3. **Хостинг для изображений:** В качестве хранилища для изображений я выбрал Google Drive, так как сервис выдает статическую ссылку на файл + много дискового пространства. Поэтому единственное что нужно было сделать для быстрого фикса всех ссылок на изображения - это взять редактор и выполнить Find & Replace All.

Напоследок еще несколько полезных ссылок по Jekyll:

* [Знакомство, установка и настройка Jekyll (rus.)](http://frontender.info/build-blog-jekyll-github-pages/)
* [Как добавить поиск Google Custom Search на блог Jekyll (engl.)](http://digitaldrummerj.me/blogging-on-github-part-7-adding-a-custom-google-search/)
* [Создание своей страницы с ошибкой 404 (engl.)](https://help.github.com/articles/creating-a-custom-404-page-for-your-github-pages-site/)
* [Создание категорий и страниц с тегами без плагина (engl.)](http://christianspecht.de/2014/10/25/separate-pages-per-tag-category-with-jekyll-without-plugins/)
* [Вывод похожих записей (engl.)](https://anmonteiro.com/2015/08/jekyll-related-posts-revamped/)
* [Темы для Jekyll](http://jekyllthemes.org/)
