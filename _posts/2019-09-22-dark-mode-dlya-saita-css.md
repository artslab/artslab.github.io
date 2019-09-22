---
layout: post
title: Добавляем поддержку темного режима (Dark Mode) для сайта
date: 2019-09-22 10:50
categories:
  - stati
author: 4gray
permalink: "/stati/dark-mode-dlya-saita-css"
tags:
  - css3
summary:
amp: false
---

Темные темы сегодня актуальны как никогда. Достаточно взглянуть на свежие версий операционных систем (например, iOS, Android, macOs) и популярных приложений, где в основных настройках можно легко переключить внешний вид со светлой на темную тему. При переключений параметр [prefers-color-scheme](https://developer.mozilla.org/ru/docs/Web/CSS/@media/prefers-color-scheme) изменяет свое значение с `light` на `dark`. Таким образом, мы можем отслеживать его в CSS коде нашего сайта/веб-приложения и написать отдельную Media Query с стилями для темного режима.

В итоге у меня получились такие варианты:

![]({{ site.baseurl }}/images/2019/dark-mode-css/dark-vs-light-theme-css.png){: .center-image }

Впрочем, если у вы используете операционную систему с включеным Dark Mode и один из [поддерживаемых браузеров](https://caniuse.com/#search=prefers-color-scheme), то вы наверняка уже заметили темные тона на моем сайте.

Для конкретного пример с CSS Media Query, оставлю здесь небольшой кусочек кода отвечающий за цвет фона и цвет шрифта в шапке:

    @media (prefers-color-scheme: dark) {
        html, body {
            color: #bfbfbf;
            background: #1a1a1a;
        }

        .blog-header {
            .blog-title,
            .blog-description {
                color: #bfbfbf;
            }
        }
        ...
    }

## Как протестировать

Переключить `prefers-color-scheme` на уровне браузера можно в Firefox версий 67+ . Для этого необходимо перейти на страницу настроек `about:config`, кликнуть правой кнопкой в списке и добавить новый integer параметр `ui.systemUsesDarkTheme` с значением 1.

![]({{ site.baseurl }}/images/2019/dark-mode-css/firefox-dark-mode-settings.png){: .center-image }

## Как быстро подобрать цвета?

Перед тем как начать прописывать стили для темной темы можно воспользоваться одним из многих браузерных дополений, которое автоматический "создаст" вариант темы для сайта. Для этого мне приглянулось дополнение [Night Eye](https://chrome.google.com/webstore/detail/night-eye-dark-mode-on-an/alncdjedloppbablonallfbkeiknmkdi) доступное для разных бразуров. В нем дополнительно можно "поиграться" с цветами и подобрать подходящий вариант для вашего сайта.

![]({{ site.baseurl }}/images/2019/dark-mode-css/color-check-night-eye.gif){: .center-image }
