---
title: Peacock для VS Code - 'подсветка' проектов разными цветами
author: 4gray
layout: post
permalink: "/vscode/raznie-zveta-dlya-vscode-projektov-peacock"
categories:
- vscode
tags:
- vscode
- editor
amp: true
image: "https://artslab.info/images/2019/peacock-vscode/peacock-dlya-vscode.png"
---

Если вам приходилось одновременно работать сразу с несколькими проектами в VS Code, то возможно сталкивались с трудностями с различием открытых проектов и возможно даже начинали редактировать файлы не того проекта. Периодически со мной такое происходит, когда у меня открыты несколько окон с веб-приложениями со схожей структурой и написанные на одном фреймворке.

Именно для таких сценариев и рассчитано дополнение [Peacock](https://marketplace.visualstudio.com/items?itemName=johnpapa.vscode-peacock). Суть в том что оно позволит выделить часть интерфейса редактора любым цветом в отдельности для каждого открытого проекта. Таким образом каждый из проектов будет ассоциироваться с указанным цветом, что позволит вам отличать открытые проекты гораздо быстрее на визуальном уровне.

<div class="center-image">
    <amp-img src="/images/2019/peacock-vscode/peacock-dlya-vscode.png" alt="Пример с четырьмя открытими проектами с разными цветовыми схемами" title="Peacock VSCode" width="800" height="597" layout="responsive"></amp-img>
    <figcaption>Peacock: Пример с открытыми проектами в VSCode и разными цветовыми схемами для панелей</figcaption>
</div>

Как показывают скриншоты дополнение не изменяет саму тему редактора, а только верхнюю панель с заголовком, боковую часть с иконками и статусную панель внизу. Цвет элементов можно указать вручную, выбрать из списка заготовок или присвоить случайно. Выбранный цвет сохраняется на уровне проекта и хранится в файле с настройками редактора - `".vscode/settings.json"`.

Для инициализаций Peacock и присваивания цвета одному из проектов, необходимо открыть командую панель (`Ctrl + Shift + P`) и например, выбрать опцию `"Peacock: Change to a Favorite Color"` для выбора цвета из заготовок.

<div class="center-image">
    <amp-img src="/images/2019/peacock-vscode/peacock-command-palette.png" alt="Peacock: Список поддерживаемых команд" title="Peacock для VSCode" width="649" height="371" layout="responsive"></amp-img>
    <figcaption>Peacock: Список поддерживаемых команд</figcaption>
</div>
