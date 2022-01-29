---
title: Подборка VSCode-дополнений для разработки Angular-приложений
author: 4gray
layout: post
date: 2019-11-10 11:03
permalink: "/category/vscode/vscode-extensions-web-razrabotka"
categories:
- angular
- vscode
amp: true
tags: 
- angular
- vscode
image: "../images/2019/vscode-extensions/night-owl-vscode.png"
---

Так как последние пару лет я активно работаю над Angular-приложениями, то в этом посте я хотел бы поделиться дополнениями для VSCode, которыми я пользуюсь ежедневно. Некоторые из них касаются именно Angular'a, а другие будут полезным любым веб-разработчикам, вне зависимости от используемого фреймворка. 

1.[File Ext Switcher](https://marketplace.visualstudio.com/items?itemName=JohannesRudolph.file-ext-switcher)(Angular Companion)

Как правило, в рамках ангуляра один компонент состоит из четырех файлов - логика компонента в ts-файле, шаблон HTML, файл со стилем и spec-файл с тестами. Данное дополнение я использую для переключения между этими 4 файлами. Особенно удобно в режиме Split Screen с двумя открытыми файлами в разных вкладках. Таким образом, с помощью горячих клавиш, можно быстро открывать разные части (файлы) компонента в соседних вкладках редактора.

2.[Angular Files](https://marketplace.visualstudio.com/items?itemName=alexiv.vscode-angular2-files)

По сути это дополнение является графической оболочкой над Angular CLI. Например, чтобы сгенерировать новый компонент, достаточно кликнуть по необходимой папке правой кнопкой мыши и выбрать `New Angular Component` из контекстного меню. Кроме самих компонентов дополнение позволяет генерировать модули, сервисы, пайпы и т.д.

<div class="center-image">
    <amp-img src="https://user-images.githubusercontent.com/1618071/38100803-0bb64a90-3387-11e8-80c9-b5c5883bfb38.gif" alt="Angular Files - быстрый доступ к Angular CLI из редактора" title="Angular Files - быстрый доступ к Angular CLI из редактора" width="850" height="504" layout="responsive"></amp-img>
    <figcaption>Angular Files - быстрый доступ к Angular CLI из редактора</figcaption>
</div>

3.[Angular Language Service](https://marketplace.visualstudio.com/items?itemName=Angular.ng-template)

Одно из базовых дополнений для Angular-разработчиков. Позволяет использовать функцию авто-дополнение и подсказок в HTML-шаблонах и ts-файлах с компонентами.

<div class="center-image">
    <amp-img src="https://github.com/angular/vscode-ng-language-service/raw/master/demo.gif" alt="Дополнение Angular Language Service" title="Дополнение Angular Language Service" width="850" height="444" layout="responsive"></amp-img>
    <figcaption>Дополнение Angular Language Service</figcaption>
</div>

4.[Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

С авто-форматированием кода лучше всех справляется prettier. На уровне проекта можно создать файл prettierrc с правилами и prettierignore с исключениями, остальные подробности в доках.

5.Линтинг
   
В зависимости от того на чем вы пишите (JS/TS) обязательными являются дополнения для линтинга кода. 
Для тайпскрипта это [TSLint](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-tslint-plugin) и для JavaScript - [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint). 
Кстати, Prettier и дополнение для линтинга могут конфликтовать друг с другом, поэтому важно настроить их правильно.

6.Работа с Git

Редактор имеет встроенную поддержку Git, но для расширения его возможностей и улучшения интеграции Гита рекомендую установить такие дополнения как: [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) и [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory).

<div class="center-image">
    <amp-img src="https://raw.githubusercontent.com/eamodio/vscode-gitlens/master/images/docs/gitlens-preview.gif" alt="Дополнение Git Lens" width="711" height="587" layout="responsive"></amp-img>
    <figcaption>Подсветка строк с Git Lens</figcaption>
</div>

7.Размер импортов

Import cost добавляет информацию о размере импортированной библиотеки прямо на строке с импортом.

<div class="center-image">
    <amp-img src="https://file-wkbcnlcvbn.now.sh/import-cost.gif" alt="Import Cost - отображает размер импортов" title="Import Cost - отображает размер импортов" width="800" height="139" layout="responsive"></amp-img>
    <figcaption>Import Cost - отображает размер импортов</figcaption>
</div>

8.Разное

* [Ident-Rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow) - подсветка отступов.
* [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) - подсвечивает парные скобки.
* [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight) - подсветка цветовых кодов в CSS-файлах и не только.
* [Auto-Close-Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag) - автоматически закрывает открытый тег.
* [Quokka](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode) - позволяет мгновенно выполнить код прямо из интерфейса редактора. Использую как альтернативу таких сервисов как JsFiddle, Codepen и т.п.
* [WakaTime](https://marketplace.visualstudio.com/items?itemName=WakaTime.vscode-wakatime) - сервис для трекинга времени проведенного в редакторе над различными проектами.
* [Peacock](https://artslab.info/vscode/raznie-zveta-dlya-vscode-projektov-peacock) - подсветка интерфейса редактора разными цветами на уровне проектов.
* [VSCode Github Trending](https://marketplace.visualstudio.com/items?itemName=4gray.vsc-github-trending) - список популярных репозиториев на Github.

9.Темы и шрифты

Что касается настройки внешнего вида редактора, то для этого существует огромное количество тем, поэтому каждый сможет подобрать что-нибудь для себя. 
Я в последнее время использую тему [Night Owl](https://marketplace.visualstudio.com/items?itemName=sdras.night-owl) вместе с шрифтом `Fira Code iScript`. 

<div class="center-image">
    <amp-img src="https://artslab.info/images/2019/vscode-extensions/night-owl-vscode.png" alt="VSCode с темой Night Owl" title="VSCode с темой Night Owl" width="850" height="527" layout="responsive"></amp-img>
    <figcaption>VSCode с темой Night Owl</figcaption>
</div>
