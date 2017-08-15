---
title: Oversetter - бесплатное приложение переводчик (macOs, Windows, Linux)
author: serEga
layout: post
permalink: /electron/oversetter-translator-app/
categories:
  - electron
  - macosx
tags:
  - electron
  - web-dev
  - javascript
amp: true
date: 2017-08-11 19:00:00
---

В рамках ознакомления с последними версиями Angular и частой необходимости использования переводчика при написаний диплома, я <del>изобрёл очередной велосипед</del> разработал небольшое приложение переводчик, которое располагается в строке меню (menubar) в macOs или в системном трее Windows. Тем самым всего в один клик по иконке можно получить быстрый доступ к приложению для перевода текста. За саму функцию перевода в Oversetter отвечает открытое API сервиса Yandex Translate. 

<center>
  <amp-img src="https://4gray.github.io/oversetter/assets/screenshot-1.png" width="612" height="418" alt="бесплатное приложение переводчик"></amp-img>
</center>

Соответсвенно для работы приложения потребуется [зарегистрировать](https://tech.yandex.com/translate/) бесплатный ключ от Яндекс'а. Ключ позволяет переводить до 1.000.000 млн. символов в день. Для ознакомления с приложением в него по-умолчанию вшит тестовый ключ, но для тех кто планирует регулярное использование, рекомендую зарегистрировать свой отдельный ключ чтобы избежать лимита.

[Код на Github](https://github.com/4gray/oversetter) / [Скачать приложение для macOs, Windows, Linux](https://4gray.github.io/oversetter/)

<center>
  <amp-img src="https://github.com/4gray/oversetter/raw/master/assets/icon.png" width="150" height="150" alt="иконка приложения"></amp-img>
</center>

Oversetter работает на базе фреймворка [Electron](https://electron.atom.io/), который позволяет использовать веб-технологий для создавания кросс-платформенные приложения. Что касается фреймворка, то один из его минусов это итоговый размер программы составляющий, как правило, не менее 120 мб (после сжатия в архив до ~45 мб). А так же потребление памяти при длительном использований.

PS: Буду рад любым отзывам :)