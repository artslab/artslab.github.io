---
title: Сборка и деплоймент веб-приложений на Github Pages с помощью Github Actions
author: 4gray
layout: post
permalink: "/angular/sborka-deployment-angular-apps-github-actions"
categories:
- angular
tags:
- angular
- github actions
amp: true
image: "../images/2019/angular-github-actions/github-action-execution-success.jpg"
---

Недавно я получил доступ к бета-версий CI-сервиса - [Github Actions](https://github.com/actions). Если раньше для использования возможностей "непрерывной интеграций" приходилось использовать такие сервисы как `Travis CI` или `Circle CI`, то теперь имея репозиторий на Github'е можно обойтись единой платформой. В этом небольшом посте я хотел бы рассмотреть пример сборки и деплоймента Angular-приложения в рамках платформы Github. 

Как и в других CI-сервисах, запуск самого CI-процесса (здесь это называется `workflow`) можно настроить [по-разному](https://help.github.com/en/articles/events-that-trigger-workflows), например, указать ветку (`master`, `develop`, `release/*` etc) из которой будет взят код и/или действие при котором будет "тригериться" наш workflow (при `merge`, `pull request`, `tag` etc.). Так же можно указать платформу для сборки нашего кода и версию инструментов для сборки, например, версию NodeJs. 

В нашем простом примере, сборка и деплоймент будут происходить после каждого git commit'a в главную ветку `master`.  Первым шагом в нашем `workflow`, станет установка всех необходимых зависимостей с помощью `$ npm install`. После этого мы запустим сборку приложения. Для этого воспользуемся Angular CLI и выполним `$ ng build --prod`. После сборки нам остается перейти в папку `/dist/<app-name>` и оттуда выполнить `"$ git push"` собранного приложения в отдельную ветку. 

Так как на Github'е нам доступен такой сервис как [Github Pages](https://pages.github.com/), то мы будем использовать ветку `gh-pages`. Таким образом Github Pages сможет подхватить контент из соответственной ветки и "захостит" его по адресу `https://<user>.github.io/<repository-slug>`. 

В качестве самого workflow для Github Actions воспользуемся заготовкой [Github Pages Deploy](https://github.com/JamesIves/github-pages-deploy-action). Для её работы нам понадобиться сделать два следующих шага:

**1. Генерируем Access Token**
Создать новый ключ доступа (`access token`) в настройках Вашего Github-аккаунта (`Settings -> Developer settings -> Personal access tokens`). Затем необходимо скопировать его и сохранить как секретную переменную под именем `ACCESS_TOKEN` в настройках репозитория проекта (`Settings -> Secret -> Add a new secret`).

<div class="center-image">
    <amp-img src="https://artslab.info/images/2019/angular-github-actions/github-action-execution-success.jpg" alt="Github: Страница настроек и создание Access Token" title="Github Settings - Accesss Token" width="802" height="432" layout="responsive"></amp-img>
    <figcaption>Github: Страница настроек и создание Access Token'а</figcaption>
</div>

**2. Создаем workflow-файл**
После этого создаем yml-файл с нашим `workflow` и используем в нем уже упомянутую заготовку. Название файла не играет роли (например, `build-and-deploy.yml`), но важно сохранить его в папке `/.github/workflows/build-and-deploy.yml`. 

Содержание файла:  
```
name: Deploy to GitHub Pages
on:
    push:
        branches:
            - master
jobs:
    build-and-deploy:
        runs-on: ubuntu-latest
        steps:
        - name: Checkout
          uses: actions/checkout@master

        - name: Build and Deploy
          uses: JamesIves/github-pages-deploy-action@master
          env:
            ACCESS_TOKEN: ${{ secrets.ACCESS_TOKEN }}
            BRANCH: gh-pages
            FOLDER: dist/<app-name>
            BUILD_SCRIPT: npm install && npm run-script build
```

PS: Не забудьте сменить путь к приложению в папке `dist/` и убедиться в том, что в package.json прописан скрипт с командой `build`. В случае с Angular-приложением в `build` скрипте нужно указать параметр `--base-href=<app-name>` с правильным путем.

<div class="center-image">
    <amp-img src="https://artslab.info/images/2019/angular-github-actions/github-action-execution-success.jpg" alt="Github Actions: Пример с выполненным workflow" title="Github Actions" width="802" height="407" layout="responsive"></amp-img>
    <figcaption>Github Actions: Пример с выполненным workflow</figcaption>
</div>

На этом всё. Если все настроено правильно, то теперь `Github Actions` будет реагировать на каждый новый коммит, при этом выполняя сборку и деплоймент новой версий вашего приложения.

[Репозиторий с примером](https://github.com/4gray/my-iptv-player-pwa/blob/master/.github/workflows/deploy-to-gh-pages.yml) | [Пример успешной сборки](https://github.com/4gray/my-iptv-player-pwa/commit/e05b7ebdfe58fe8b4bb8a169eaa8c0ab62947a32/checks?check_suite_id=253660159)

