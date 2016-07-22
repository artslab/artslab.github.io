---
id: 7895
title: 'Создаем кнопку для прокрутки страницы вверх (CSS &#038; jQuery)'
date: 2013-09-09T14:24:25+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7895
permalink: /snippety/sozdaem-knopku-dlya-prokrutki-stranicy-vverx-css-jquery/
cover:
  -
wpb_post_views_count:
  - 1227
dsq_thread_id:
  - 1739682623
categories:
  - snippety
tags:
  - css
  - jquery
  - js
  - сниппет
---
Несмотря на то, что существует ряд готовых jQuery- плагинов позволяющих создать кнопку/панельку для прокрутки сайта вверх (с разными визуальными эффектам), сегодня мы сами создадим такую кнопочку, для того чтобы понять как она работает, а заодно и познакомиться с некоторыми аттрибутами CSS и функциями jQuery. <a href="http://codepen.io/4gray/pen/Legov" target="_blank">Демо</a> доступно в песочнице.

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/prokrutit_sait_vverh.png"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/prokrutit_sait_vverh-300x183.png" alt="панель для прокутки сайта вверх" class="aligncenter size-medium wp-image-7896" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/prokrutit_sait_vverh-300x183.png 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/prokrutit_sait_vverh.png 571w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>


<!--more-->

Начнем с HTML-части. Здесь все просто, для примера я поместил содержание в блок с классом .content, а за нашу кнопку отвечает класс .go-top.

{% highlight html %}

<div id="content">

<h2>Заголовок</h2>

<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>

<img src="http://placeimg.com/300/200/people" />

</div>

<div class="go-top"></div>

{% endhighlight %}

В данном примере я создал не кнопку, а целый область занимающий левую часть экрана (как ВКонтакте). Как только пользователь прокрутит страницу на X пикселей вниз, он увидит нашу панельку с иконкой стрелочки, которая при клике прокрутит страницу наверх и снова исчезнет.

{% highlight css %}

#content{
  width:300px;
  display:block;
  margin: 0 auto;
  background: #fff;
  padding: 5px 20px;
}

.go-top {
  position:fixed;
  bottom: 2px;
  left:0px;
  background: #333;
  padding:20px;
  display:none;
  color: #fff;
  cursor: pointer;
  height: 100%;
  opacity: 0.4;
  -webkit-opacity: 0.4;
  -moz-opacity: 0.4;
  width:100px;
}

.go-top:after {
  content: &#8216;\25B2&#8217;;
  position: absolute;
  bottom:10px;
  left: 50px;
  font-size: 32px;
  font-weight:100;
}

{% endhighlight %}

И последняя часть кода это jQuery. Здесь стоит отметить два главных события это scroll() &#8211; то, что должно происходить при прокрутке страницы и click() &#8211; действие по клике на нашу кнопку. Функция scrollTop() возвращает позицию, насколько страницы прокручена вниз.

{% highlight javascript %}

$(function(){

  $(window).scroll(function(){
      var scrolled = $(window).scrollTop();

      if (scrolled > 200) $(&#8216;.go-top&#8217;).fadeIn(&#8216;slow&#8217;);
      if (scrolled < 200) $(&#8216;.go-top&#8217;).fadeOut(&#8216;slow&#8217;);
    });

    $(".go-top").click(function () {
    $("html, body").animate({ scrollTop: "0" },200);
  });

});

{% endhighlight %}

(scrolled > 200) &#8211; обозначает, что наша панелька будет появляться только после того, как пользователи прокрутит страницу ровно на более чем 200 пикселей вниз. Конечно же, эту цифру можно смело изменить, в зависимости от ваших потребностей.

  <h4>Демо:</h4>

<p data-height="268" data-theme-id="414" data-slug-hash="Legov" data-user="4gray" data-default-tab="result" class='codepen'>
  See the Pen <a href='http://codepen.io/4gray/pen/Legov'>Back to Top Button (CSS & jQuery)</a> by 4gray (<a href='http://codepen.io/4gray'>@4gray</a>) on <a href='http://codepen.io'>CodePen</a>
</p>