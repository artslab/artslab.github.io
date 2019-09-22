---
title: Создаем свою Angular библиотеку с UI компонентами
date: 2018-12-25 00:00:00 +0100
author: 4gray
layout: post
permalink: "/angular/create-angular-components-library"
categories:
  - angular
tags:
  - angularjs
  - javascript
amp: false
---

Поработав какое-то время с фреймворком (в нашем случае речь пойдет о Angular) и разработав несколько приложений, рано или поздно приходишь к пониманию того, что многие компоненты можно сделать универсальными и вынести в свою отдельную библиотеку. В этой небольшой статье я хотел бы рассмотреть возможность создания такой библиотеки с помощью Angular CLI.
Если вкратце, то отдельные шаги выглядят так:

1. Создание нового проекта и генерация библиотеки
2. Создание первого компонента и сборка библиотеки
3. Публикация библиотеки на npmjs ([результат](https://www.npmjs.com/package/arts-lib))

## 1. Создание нового проекта и генерация библиотеки

Если у вас ещё не установлен инструмент для командной строки @angular/cli, то первым делом устанавливаем его и создаём новый проект через командуную строку.

    $ npm i -g @angular/cli
    # или обновляем @angular/cli до последней версий с помощью команды $ npm install -g @angular/cli@latest
    $ ng new my-lib

Теперь у нас есть приложение, которое будет использовано в качестве демо для нашей библиотеки. В нем мы создадим отдельный проект для библиотеки компонентов. Возвращаемся в командную строку и сгенерируем проект библиотеки (дополнительно укажем префикс для компонентов библиотеки):

    $ ng generate library arts-lib --prefix=al

После выполнения этих команд должна появиться примерно такая структура файлов и папок:

![скриншот visual studio code демонстрирубщий структуру приложения]({{ site.baseurl }}/forestryio/images/angular-library-structure.jpg "структура библиотеки")

PS: Можно сразу удалить стандартный компонент с сервисом и тестами (файлы arts-lib.\*\*\*.ts в папке ./projects/arts-lib/src/lib, и их импорты из ./projects/arts-lib/src/lib/public_api.ts и ./projects/arts-lib/src/lib/arts-lib.module.ts).

## 2. Создание компонента и сборка библиотеки

Пришло время создать наш первый компонент. В качестве примера, предлагаю создать обычную кнопку. Для этого перейдем в командную строки и используем angular cli для быстрого создания компонента. Первым делом сгенерируем модуль для нашей кнопки. Нужно это для того чтобы в будущем иметь возможность импорта только необходимых нам компонентов, а не всей библиотеки сразу:

    $  ng g m button --project=arts-lib

И теперь сам компонент:

    $ ng g c button --project=arts-lib

Так как мы указали название нашего проекта с библиотекой, то и появиться он в соответствующей папке.

Кнопке добавим одну единственную переменную в качестве параметра, в которой будем передавать нужный нам тип кнопки (success, warn и info) привязанный к трем различным цветам. А так же event который будет срабатывать по клику.

В итоге у меня получился следующий компонент:

    import { Component, OnInit, Input, Output, EventEmitter } from '@angular/core';

    @Component({
        selector: 'al-button',
        template: `
            <button [class]="type" (click)="buttonClick.emit($event)">
                <ng-content></ng-content>
            </button>
        `,
        styleUrls: ['./button.component.css']
    })
    export class ButtonComponent {

        /**
         * Type of the button
         */
        @Input() type: 'success' | 'info' | 'warn';

        /**
         * Button click event
         */
        @Output() buttonClick = new EventEmitter<MouseEvent>();

    }

Плюс небольшой css файл с стилем и цветами кнопки:

    button {
        border-radius: 4px;
        box-shadow: 0px 3px 1px #ccc;
        padding: 5px 10px;
        border: none;
        border-radius: 2px;
        font-size: 1em;
        cursor: pointer;
        margin: 5px;
        color: #fff;
    }
    button:hover {
        box-shadow: 0px 3px 1px #999;
    }
    .success {
        background: #18a718;
    }
    .info {
        background: #7969e8;
    }
    .warn {
        background: #ff614c;
    }

Компонент готов, осталось импортировать его в два модуля

1. В файл arts-lib.module.ts:

   import { NgModule } from '@angular/core';
   import { ButtonModule } from 'arts-lib/arts-lib';

   @NgModule({
   imports: [
   ButtonModule
   ],
   exports: [
   ButtonModule
   ]
   })
   export class ArtsLibModule { }

2. В файл public_api.ts:

   /\*
   _ Public API Surface of arts-lib
   _/

   export \* from './lib/button/button.module';

Готово, собираем библиотеку в Angular-формате, который будет подходить для ее импорта в других приложения.

    $ ng build arts-lib

Что же, теперь предлагаю проверить кнопку в нашем демо-проекте. Для этого находим файл app.component.html и добавляем туда наш компонент в нескольких цветах и привяжем функцию для клика:

    <al-button color="success" (buttonClick)="alert($event)"></al-button>
    <al-button color="warn" (buttonClick)="alert($event)"></al-button>
    <al-button color="info" (buttonClick)="alert($event)"></al-button>

В модуле демо-приложения соответственно нужно импортировать нашу библиотеку с модулем кнопки. Для этого открываем файл app.module.ts и добавляем следующее:

    import { BrowserModule } from '@angular/platform-browser';
    import { NgModule } from '@angular/core';

    import { AppComponent } from './app.component';
    import { ButtonModule } from 'arts-lib'; // <-- импорт модуля с кнопокой из библиотеки

    @NgModule({
    declarations: [
        AppComponent
    ],
    imports: [
        ButtonModule,
        BrowserModule // <- импорт модуля с компонентом в приложение
    ],
    providers: [],
    bootstrap: [AppComponent]
    })
    export class AppModule { }

Импортируем нашу кнопку в демо-приложение и запускаем его из командной строки с помощью команды "ng serve". Открываем [localhost:4200](http://localhost:4200) в бразуере для того чтобы проверить результат, должно получиться примерно так:

![]({{ site.baseurl }}/forestryio/images/angular-library-component.png)

## Публикация библиотеки на npmjs

Для того чтобы опубликовать нашу библиотеку в качестве npm-модуля на npmjs, первым делом нам понадобиться [зарегистрироваться](https://www.npmjs.com/signup) на этом сайте. После этого переходим в командую строку и авторизируемся с помощью команды "npm login". Теперь перед тем как опубликовать нашу библиотеку, нужно убедиться в правильной версий, укажем вручную 1.0.0 или воспользуемся командой "\$ npm version major" и увеличим major версию приложения. Так же следует указать и другие метаданные в файле package.json, например описание проекта, имя автора, адрес репозитория, лицензию и прочее.

Небольшое отступление, в качестве системы для автоматизированного управления версиями и генераций changelog'ов для ваших приложениях рекомендую использовать связку [semantic-release](https://github.com/semantic-release/semantic-release) + [commitlint](https://github.com/marionebl/commitlint) + [husky](https://github.com/typicode/husky) и при этом придерживаться одного стиля для сообщения в git коммитах (мне нравится Angular Commit Message Format), но это уже тема для отдельной статьи :-)

И последнее, перед тем как опубликовать библиотеку было бы неплохо отредактировать стандартный файл README.md и описать в нем возможности публикуемого проекта.

Наконец, переходим в папку с собранной библиотекой:

    $ cd dist/arts-lib

И выполняем команду для публикаций:

    $ npm publish

Дожидаемся сообщения о успешной публикаций и переходим по ссылке в браузер чтобы посмотреть на наш модуль. У меня получилось так:

[https://www.npmjs.com/package/arts-lib](https://www.npmjs.com/package/arts-lib "https://www.npmjs.com/package/arts-lib")

Теперь для того чтобы использовать компоненты из нашей библиотеки в стороннем проект достаточно установить ее с помощью:

    npm i arts-lib

И затем импортировать модуль с нужным компонентом:

    import { ButtonModule } from 'arts-lib';

На этом всё, если упустил что-то важное, то буду рад любым отзывам в комментариях.

[Код проекта на Github](https://github.com/artslab/arts-lib)
