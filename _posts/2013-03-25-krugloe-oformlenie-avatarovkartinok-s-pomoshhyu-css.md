---
id: 6719
title: Круглое оформление аватаров/картинок с помощью CSS
date: 2013-03-25T21:24:35+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=6719
permalink: /snippety/krugloe-oformlenie-avatarovkartinok-s-pomoshhyu-css/
cover:
  - 6729
wpb_post_views_count:
  - 3370
dsq_thread_id:
  - 1566542866
categories:
  - snippety
tags:
  - css
  - html
  - дизайн
---
<center>
  <img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/rounded_css_avatar.jpg" alt="border-radius круглые картинки" class="aligncenter size-medium wp-image-6742" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/rounded_css_avatar.jpg 542w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/rounded_css_avatar-300x71.jpg 300w" sizes="(max-width: 542px) 100vw, 542px" />
</center>

Если Вам надоело стандартное, квадратное оформление аватаров или миниатюр новостей в Вашем блоге, то можно легко &#8220;закруглить&#8221; картинки и придать им другой вид, используя для этого только средства CSS.

<!--more-->





<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari-300x135.jpg" alt="круглые аватары в комментариях" class="aligncenter size-medium wp-image-6721" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari-300x135.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari.jpg 655w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Если внимательно приглядеться к картинке выше, то можно разглядеть не только круглый аватар, но и несколько других элементов и эффектов. Во-первых, это рамка в которой находится аватар, во-вторых внутреннюю тень, а так же выпуклость и эффект стекла, в виде светлого отблеска на аватаре. Код такого оформления мы рассмотрим чуть ниже, а для начала ознакомимся с простым примером.

<center>
  <img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/zakruglenie_kartinke.jpg" alt="сделать картинку круглой css" class="aligncenter size-medium wp-image-6723" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/zakruglenie_kartinke.jpg 418w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/zakruglenie_kartinke-300x72.jpg 300w" sizes="(max-width: 418px) 100vw, 418px" />
</center>

Допустим мы хотим закруглить края изображения. Для этого достаточно будет добавить всего лишь одно CSS-свойство &#8211; border-radius.

HTML-код:

{% highlight html %}<img class="avatar" src="http://placeimg.com/80/80/people" />{% endhighlight %}

Стиль CSS:

{% highlight css %}
.avatar {
  width: 80px;
  height: 80px;
  border-radius: 40px; /\* половина ширины и высоты \*/
}
{% endhighlight %}

<a href="http://codepen.io/4gray/pen/rgEmj" target="_blank">Демо на Codepen</a>

### Стильное оформление аватара

Теперь рассмотрим полный пример.

[<img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari-300x135.jpg" alt="круглые аватары в комментариях" class="aligncenter size-medium wp-image-6721" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari-300x135.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari.jpg 655w" sizes="(max-width: 300px) 100vw, 300px" />](http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/kruglie_avatari.jpg)

Для начала подготовим часть HTML-кода:

{% highlight html %}

<div id="avatarbg">

<img class="avatar" src="http://placeimg.com/90/90/animals" />

</div>

{% endhighlight %}

Перейдем к CSS-стилям:

{% highlight css %}

/\* Тень \*/

#avatarbg img.avatar {
  margin: 0;
  -webkit-box-shadow: 0 1px 2px rgba(0,0,0,0.3);
  -moz-box-shadow: 0 1px 2px rgba(0,0,0,0.3);
  box-shadow: 0 1px 2px rgba(0,0,0,0.3);
  width: 68px;
  height: 68px;
}

/\* Фон, рамка для аватара \*/

#avatarbg {
  width: 67px;
  height: 67px;
  display: block;
  background-color: #eee;
  background-image: -moz-linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.05));
  background-image: -webkit-gradient(linear,0 0,0 100%,from(rgba(0,0,0,0)),to(rgba(0,0,0,0.05)));
  background-image: -webkit-linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.05));
  background-image: -o-linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.05));
  background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.05));
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr=&#8217;#00000000&#8242;,endColorstr=&#8217;#0d000000&#8242;,GradientType=0);
  padding: 6px;
  padding-top: 5px;
  -webkit-box-shadow: 0 1px 0 #fff,0 -1px 0 rgba(0,0,0,0.4);
  -moz-box-shadow: 0 1px 0 #fff,0 -1px 0 rgba(0,0,0,0.4);
  box-shadow: 0 1px 0 #fff,0 -1px 0 rgba(0,0,0,0.4);
  border: 1px solid #c0d6e0;
  position: relative;
  -webkit-transition: all .2s ease-in-out 0s;
  -moz-transition: all .2s ease-in-out 0s;
  -o-transition: all .2s ease-in-out 0s;
  transition: all .2s ease-in-out 0s;
  float:left;
}

/\* Выпуклость \*/

#avatarbg:before {
  background-image: -moz-linear-gradient(top,rgba(255,255,255,0.4),rgba(255,255,255,0));
  background-image: -webkit-gradient(linear,0 0,0 100%,from(rgba(255,255,255,0.4)),to(rgba(255,255,255,0)));
  background-image: -webkit-linear-gradient(top,rgba(255,255,255,0.4),rgba(255,255,255,0));
  background-image: -o-linear-gradient(top,rgba(255,255,255,0.4),rgba(255,255,255,0));
  background-image: linear-gradient(top,rgba(255,255,255,0.4),rgba(255,255,255,0));
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr=&#8217;#66ffffff&#8217;,endColorstr=&#8217;#00ffffff&#8217;,GradientType=0);
  -webkit-box-shadow: inset 0 1px 0 #fff,inset 0 -1px 7px rgba(0,0,0,.2);
  -moz-box-shadow: inset 0 1px 0 #fff,inset 0 -1px 7px rgba(0,0,0,.2);
  box-shadow: inset 0 1px 0 #fff,inset 0 -1px 7px rgba(0,0,0,.2);
  border: 1px solid #afc3cb;
}

/\* Блеск, эффект стекла \*/

#avatarbg:after {
  background: -webkit-gradient(linear,left top,right bottom,color-stop(0%,rgba(255,255,255,0.1)),color-stop(44%,rgba(255,255,255,0.2)),color-stop(45%,rgba(255,255,255,0)),color-stop(100%,rgba(255,255,255,0)));
}

#avatarbg:before, #avatarbg:after {
  content: "";
  width: 68px;
  height: 68px;
  position: absolute;
  left: 4px;
  top: 4px;
}

/\* Закругление \*/

#avatarbg, #avatarbg:before, #avatarbg:after, #avatarbg img.avatar {
  -webkit-border-radius: 81px;
  -moz-border-radius: 81px;
  border-radius: 81px;
  -moz-background-clip: padding;
  -webkit-background-clip: padding-box;
  background-clip: padding-box;
}

{% endhighlight %}

Результат и код можно также посмотреть на моей страничке на <a href="http://codepen.io/4gray/pen/iBpLm" target="_blank"сервисе codepen</a>.

Если вы ищете другие полезные сниппеты, то загляните в рубрику на нашем сайте.