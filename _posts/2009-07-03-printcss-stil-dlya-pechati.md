---
id: 404
title: 'Print.css &#8211; стиль для печатной версий сайта'
date: 2009-07-03T04:22:39+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=404
permalink: /sovetyi/printcss-stil-dlya-pechati/
ljID:
  - 235
prosmotr:
  - 164
wpb_post_views_count:
  - 1668
dsq_thread_id:
  - 1565016218
categories:
  - sovetyi
tags:
  - css
---
<center>
  <a href="{{site.img_cdn}}/otdelnii_stil_dlya_pechati_teksta.png"><img src="{{site.img_cdn}}/otdelnii_stil_dlya_pechati_teksta.png" alt="" title="otdelnii_stil_dlya_pechati_teksta" width="468" height="145" class="aligncenter size-full wp-image-5753" srcset="{{site.img_cdn}}/otdelnii_stil_dlya_pechati_teksta.png 468w, {{site.img_cdn}}/otdelnii_stil_dlya_pechati_teksta-300x92.png 300w" sizes="(max-width: 468px) 100vw, 468px" /></a>
</center>

Я заметил на многих сайтах (<del datetime="2011-04-08T18:43:19+00:00">в том числе и на моем блоге</del> уже появился) отсутствует отдельный стиль для печати. То есть, если кто-то захочет распечатать какой-либо материал с сайта (например, отпечатать эту статью), то на бумаге он будет выглядеть почти так же как и в сети, вместе с кучей ненужной информацией, фоновой картинкой и лишними изображениями. С боковой панелью, с категориями, с облаком тегов и прочими ссылками и кнопочками, которые будут не интересны на бумаге. А на картриджах для домашнего принтера, все таки стоит экономить, так как цены для некоторых моделей очень даже кусаются =)

Так вот, для того чтобы это исправить, создадим отдельный css файл и назывем его print.css. Пропишем путь к этому файлу в header страницы:

[sourcecode language=&#8217;html&#8217;]

<link rel="stylesheet" href="print.css" type="text/css" media="print" />
[/sourcecode]

С его помощью мы спрячем все не нужные блоки, кнопочки, панельки и т.д. Делаем это с помощью css-параметра display, которому задаем значение none.

Например:

[sourcecode language=&#8217;css&#8217;]#sidebar {

display:none;

}[/sourcecode]

Так же можно изменить размеры текста на нормальные/стандартные, там где они были слишком большими. Изменить, а лучше совсем убрать выделяющийся цвет ссылок, убрать их подчеркивание и т.д.

Для того чтобы просмотреть как сайт будет выглядеть в отпечатанном виде, достаточно выбрать &#8220;предварительный просмотр&#8221; в меню браузера.

Надеюсь эти советы помогут Вам в созданий печатной версий Вашего сайта =)