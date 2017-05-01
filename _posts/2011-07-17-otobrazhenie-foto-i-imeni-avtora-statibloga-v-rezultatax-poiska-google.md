---
id: 3729
title: Отображение фотографии и имени автора статьи/блога в результатах поиска Google
date: 2011-07-17T15:04:48+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=3729
permalink: /stati/otobrazhenie-foto-i-imeni-avtora-statibloga-v-rezultatax-poiska-google/
ljID:
  - 445
prosmotr:
  - 138
wpb_post_views_count:
  - 5460
dsq_thread_id:
  - 1565025151
categories:
  - stati
tags:
  - google
  - поиск
---
<center>
  <a href="{{site.img_cdn}}/google_author_name_photo_in_serp.jpg"><img src="{{site.img_cdn}}/google_author_name_photo_in_serp.jpg" alt="Google начал отображать фотографию и имя автора статьи в результатах поиска" title="google_author_name_photo_in_serp" width="574" height="86" class="alignnone size-full wp-image-3735" /></a>
</center>

Еще одна новинка от гугла. Теперь стало возможным выводить **фотографию и имя автора статьи блога, прямо в выдаче результатов(SERP) на Google** ([пример](http://www.google.com/search?q=site:daggle.com)). Одного взгляда на картинку выше, должно хватить для более понятного представления. Единственное требование для этого, это наличие своего профиля на Google ([profiles.google.com](http://profiles.google.com/)), так как картинка и имя, берутся именно оттуда. Такой хитрый шаг со стороны гугла.

Давайте сразу перейдем к реализаций. Тут в принципе все просто и понятно.

1. Необходимо создать страницу на блоге &#8220;[О себе](http://artslab.info/contact/)&#8221; и разместить на ней ссылку на профиль гугла, с параметром rel=&#8221;me&#8221;.

Например:

[sourcecode language=&#8221;html&#8221;]<a href="https://profiles.google.com/112918443114281605164" rel="me">Мой профиль Google+</a>[/sourcecode]

_Не забудьте сменить на свои id_

2. Необходимо добавить ссылку на эту страницу (&#8220;О себе&#8221;), в каждую статью блога. В случае если блога на Wp, то можно вставить либо в sidebar.php, либо под каждую статью в single.php. Мой пример:

[sourcecode language=&#8221;html&#8221;]<a href="http://artslab.info/contact/" rel="author">Автор статьи</a>[/sourcecode]

_Важен параметр rel=&#8221;author&#8221;_

3. Так же, необходимо добавить ссылку на страницу &#8220;О себе&#8221;, в блок ссылки на странице [профиля Google](https://profiles.google.com).

<center>
  <a href="{{site.img_cdn}}/google_profile_pokaz_info_pro_avtora.jpg"><img src="{{site.img_cdn}}/google_profile_pokaz_info_pro_avtora-235x300.jpg" alt="Отображение информации о авторе блога в результах поиска" title="google_profile_pokaz_info_pro_avtora" width="235" height="300" class="alignnone size-medium wp-image-3730" srcset="{{site.img_cdn}}/google_profile_pokaz_info_pro_avtora-235x300.jpg 235w, {{site.img_cdn}}/google_profile_pokaz_info_pro_avtora.jpg 358w" sizes="(max-width: 235px) 100vw, 235px" /></a>
</center>

4. Теперь идем и проверяем, правильно ли расставлены ссылки. Переходим на инструмент проверки сниппетов [Rich Snippets Testing Tool](http://www.google.com/webmasters/tools/richsnippets). Вставляем туда ссылку на любую статью и смотрим на результат. Если статья прошла верификацию значит вы все сделали правильно.

<center>
  <a href="{{site.img_cdn}}/google_profile_pokaz_info_pro_avtora_proverka.jpg"><img src="{{site.img_cdn}}/google_profile_pokaz_info_pro_avtora_proverka-300x207.jpg" alt="отображение фото автора статьи в SERP google" title="google_profile_pokaz_info_pro_avtora_proverka" width="300" height="207" class="alignnone size-medium wp-image-3731" srcset="{{site.img_cdn}}/google_profile_pokaz_info_pro_avtora_proverka-300x207.jpg 300w, {{site.img_cdn}}/google_profile_pokaz_info_pro_avtora_proverka.jpg 612w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Теперь осталось дождаться пока робот заново проиндексирует ваш сайт и они обновятся в индексе. Сам сегодня только добавил, ждем-с 🙂

([Информация о Authorship на Google](http://www.google.com/support/webmasters/bin/answer.py?answer=1229920) на англ.)