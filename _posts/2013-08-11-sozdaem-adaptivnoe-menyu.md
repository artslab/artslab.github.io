---
id: 7384
title: Создаем адаптивное меню
date: 2013-08-11T21:14:36+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7384
permalink: /snippety/sozdaem-adaptivnoe-menyu/
cover:
  - 7476
wpb_post_views_count:
  - 2863
dsq_thread_id:
  - 1599392067
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
categories:
  - Сниппеты
tags:
  - css
  - html
  - js
  - menu
---
В добавку к [прошлой записи](http://artslab.info/snippety/sozdaem-fiksirovannoe-navigacionnoe-menyu-otobrazhaemoe-pri-prokrutke-stranicy/ "Создаем фиксированное навигационное меню, отображаемое при прокрутке страницы"), еще один небольшой пример с простой адаптивной менюшкой. Будем использовать CSS Media Query + jQuery. Демо с кодом, как всегда на <a href="http://codepen.io/4gray/pen/FEujv" target="_blank">Codepen</a>, в продолжений поста более подробное, пошаговое описание.

<center>
  <a href="http://img.artslab.info/adaptivnoe_menu_css.jpg"><img src="http://img.artslab.info/adaptivnoe_menu_css-300x195.jpg" alt="адаптивное меню" class="aligncenter size-medium wp-image-7400" srcset="http://img.artslab.info/adaptivnoe_menu_css-300x195.jpg 300w, http://img.artslab.info/adaptivnoe_menu_css-1024x668.jpg 1024w, http://img.artslab.info/adaptivnoe_menu_css.jpg 1199w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>


  
<!--more-->

1. Создадим обычный Unordered List и для начала разместим в нем два div-контейнера. Первый для значка меню (три горизонтальные полоски, возьмем для этого символ Unicode &#8211; &#9776;). Иконка будет видна только на маленьких экранах.    

  
Во второй контейнер поместим все элементы/ссылки меню. У меня получился такой HTML-код:

[html]
  
<ul id="menu">
    
<div class="icon">&#9776;</div>
    
<div class="items">
      
<li><a href="#">Главная</a></li>
      
<li><a href="#">Категорий</a></li>
      
<li><a href="#">О сайте</a></li>
      
<li><a href="#">Контакт</a></li>
    
</div>
  
</ul>
  
[/html]

2. Теперь займемся CSS. Для больших экранов скроем иконку меню (display:none в классе icon) и оставим только список с ссылками. В Media Query для класса icon, соответственно, пропишем display:block, для отображения иконки на маленьком экране.

[css]
  
* {
    
padding:0;
    
margin:0;
    
font: 14px Helvetica, Arial;
  
}
  
#menu {
    
background: #c0392b;
    
width: 100%;
    
padding: 20px 0;
    
text-align: center;
  
}
  
#menu a {
    
color: #fff;
    
text-decoration: none;
  
}
  
#menu a:hover {
    
color: #ccc;
  
}
  
#menu ul {
    
padding:0;
    
margin:0;
  
}
  
.items li {
    
list-style: none;
    
display:inline;
    
padding-right: 15px;
    
width:100%;
    
margin: 0 auto;
  
}
  
.icon {
    
color: #fff;
    
cursor: pointer;
    
display: none;
    
font-size:24px;
  
}
  
.showitems {
    
display:block !important;
  
}
  
@media screen and (max-width: 800px) {
    
.icon {
       
display:block;
    
}
     
.items {
      
display:none;
    
}
    
.items li {
      
display:table;
      
padding:10px 0;
    
}
  
}
  
[/css]

<center>
  <a href="http://img.artslab.info/css_jquery_menu.jpg"><img src="http://img.artslab.info/css_jquery_menu-300x231.jpg" alt="создаем меню на css и jquery" class="aligncenter size-medium wp-image-7410" srcset="http://img.artslab.info/css_jquery_menu-300x231.jpg 300w, http://img.artslab.info/css_jquery_menu.jpg 660w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

3. JS-часть будет отвечать за раскрытие списка меню при клике на иконку в уменьшенной/мобильной версий сайта. Для отображения/скрытия списка меню, мы будем использовать две функций addClass() и removeClass(), которые будут добавлять/удалять класс showitems в зависимости от значения селектора-псевдокласса is(&#8216;:visible&#8217;).

Код:

[js]
  
$(function() {
    
$(&#8216;.icon&#8217;).click(function() {
      
if($(&#8216;.items&#8217;).is(&#8216;:visible&#8217;)) {
        
$(&#8216;.items&#8217;).removeClass(&#8216;showitems&#8217;);
      
}
      
else {
        
$(&#8216;.items&#8217;).addClass(&#8216;showitems&#8217;);
      
}
   
});
  
});
  
[/js]

<center>
  <a href="http://img.artslab.info/CodePen_-_A_Pen_by_4gray-3.png"><img src="http://img.artslab.info/CodePen_-_A_Pen_by_4gray-3-300x300.png" alt="раскрытое меню" class="aligncenter size-medium wp-image-7403" srcset="http://img.artslab.info/CodePen_-_A_Pen_by_4gray-3-300x300.png 300w, http://img.artslab.info/CodePen_-_A_Pen_by_4gray-3-100x100.png 100w, http://img.artslab.info/CodePen_-_A_Pen_by_4gray-3.png 507w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>


  


<center>
  <i>Раскрытое меню</i>
</center>

<a href="http://codepen.io/4gray/pen/FEujv" target="_blank">Демо с кодом</a>