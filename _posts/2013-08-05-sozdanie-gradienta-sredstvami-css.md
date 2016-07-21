---
id: 7307
title: Создание градиента средствами CSS
date: 2013-08-05T23:32:21+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7307
permalink: /snippety/sozdanie-gradienta-sredstvami-css/
cover:
  - 
wpb_post_views_count:
  - 783
dsq_thread_id:
  - 1573710835
categories:
  - Сниппеты
tags:
  - css3
  - gradient
---
Сегодня хочу поделиться небольшим сниппетом, который позволит с помощью всего нескольких строк CSS создать простой градиент без лишней графики. Для этого мы используем свойство box-shadow. С небольшой хитростью мы сможем применить его для имитаций плавного градиента. Далее код с примером.

<!--more-->

Создадим небольшой div-контейнер с фиксированным размером.

[html]
  
<div class="gradient"></div>
  
[/html]

Теперь создадим класс «gradient» для заполнения нашего контейнера градиентом. Свойство box-shadow предназначено для создания тени блока, но мы воспользуемся им немного иначе.
  
При указаний параметра inset у нас получится внутренняя тень. Зальем весь контейнер одним цветом, а в качестве второго цвета градиента используем нашу &#8220;тень&#8221;.

Получается такой класс:

[css]
  
.gradient {
  
background: #57e15f;
  
box-shadow: inset 0 200px 200px -100px #255f29;
  
-webkit-box-shadow: inset 0 200px 200px -100px #255f29;
  
-moz-box-shadow: inset 0 200px 200px -100px #255f29;
  
display:block;
  
width: 100%;
  
height: 200px;
  
}
  
[/css]

Результат:

<div class="gradient_example">
  <h2>
    ArtsLab
  </h2>
  
  <p>
    Создание градиента с помощью CSS
  </p>
</div>



Поиграться с кодом примера можно на [Codepen](http://codepen.io/4gray/pen/JwiGl)