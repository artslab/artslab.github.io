---
title: Быстрый переход на другую версию NodeJs с помощью NVM
date: 2019-09-27T22:00:00.000+00:00
author: 4gra
layout: post
permalink: smena-versii-nodejs-s-pomoshyu-nvm
categories: []
tags: []
amp: true

---
Иногда при разработке для nodejs бывает необходимо перейти с одной версий node на другую. Например, для того чтобы протестировать работоспособность какой-либо фичи или проверить насколько быстро она работает в определенной версий. Удобнее и быстрее всего это можно сделать с помощью инструмента под названием [Node Version Manager (NVM)](https://github.com/nvm-sh/nvm).

Для установки под Linux/MacOs заходим в терминал и выполняем комманду:

    $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash

После этого открываем .bashrc или .zshrc в зависимости от того что вы используете и экспортируем NVM в path:

    $ export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm

Для того чтобы переключиться на необходимую версию node для начала нужно скачать и установить ее:

    $ nvm install 12

Теперь переключаемся на нее:

    $ nvm use 12

И проверяем используемую версию:

    $ node --version

PS: Оставлю здесь ссылку на еще одну утилиту с аналогичным функционалом и скромным названием в видео одной буквы - [n](https://github.com/tj/n "https://github.com/tj/n")