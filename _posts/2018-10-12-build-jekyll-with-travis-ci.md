---
title: Сборка и деплоймент Jekyll-блога с помощью Travis CI
date: 2018-10-12 00:00:00 +0000
author: 4gray
layout: post
permalink: "/jekyll/build-and-deploy-jekyll-with-travis-ci/"
categories:
- jekyll
tags:
- jekyll
- deployment
amp: false

---
В одном из прошлых постов речь шла о локальной сборке блога на основе Jekyll, а так же о 'встроенной' сборке в самом репозиторий на Github Pages. В этот раз я хотел бы рассмотреть возможность автоматический сборки и деплоймента блога используя сервис Continious Integration - [Travis CI](https://travis-ci.org/).

Первый возникающий вопрос: что нам это дает?

* Во-первых появится возможность использовать любые дополнительные плагины, которые в целях безопасности не могут быть использованы при обычной сборке GitHub Pages.
* Во-вторых мы все ещё можем пользоваться онлайн сервисами для написания и редактирования постов, вроде prose.io или forestry.io.
* И в третьих данный подход позволит соблюдать, на мой взгляд, правильную структуру, такую же как и при локальном build'е. В master-branch у нас будут находиться "исходники" блога вместе с конфигурацией, а в branch'е "gh-pages" будет храниться сгенерированная версия блога, которая и будет использоваться для отображения.

Теперь рассмотрим конкретный пример. Для этого возьмём симпатичную темку (клон сервиса Ghost) под названием jasper2.

1. Fork'аем репозиторий с темой: [https://github.com/jekyller/jasper2](https://github.com/jekyller/jasper2 "https://github.com/jekyller/jasper2")
2. Сгенерируем токен на гитхабе, который будем использовать на Travis CI для доступа к нашему репозиторию с темой. Переходим на страницу -[https://github.com/settings/tokens](https://github.com/settings/tokens "https://github.com/settings/tokens") и нажимаем на "Generate new token". На открывшейся страничке ставим галочку напротив Repo, подтверждаем и копируем сгенерированный ключ.

   ![]({{ site.baseurl }}/forestryio/images/github-generate-token.png)
3. Переходим на travis-ci и если у вас нет аккаунта, то регистрируемся с помощью своего Github-аккаунта. Теперь переходим в настройки и активируем build для нашего репозитория. Там же в настройках создаём новую Environment Variable, присваиваем ей имя GITHUB_TOKEN и вставляем скопированный токен в значение переменной.

   ![]({{ site.baseurl }}/forestryio/images/add-env-variable-travis-ci.png)
4. Переходим обратно в наш репозиторий с темой jasper2, открываем/создаём файл .travis.yml и вставляем в него следующее содержание:

   {% highlight html linenos %} 

   {% raw %}

   language: ruby
   cache: bundler
   branches:
   only:
   * master

   script:
   * JEKYLL_ENV=production bundle exec jekyll build --destination site

   deploy:
   provider: pages
   local-dir: ./site
   target-branch: gh-pages
   email: deploy@travis-ci.org
   name: Deployment Bot
   skip-cleanup: true
   github-token: $GITHUB_TOKEN
   keep-history: true
   on:
   branch: master

   {% endraw %}

    {% endhighlight %}
5. В последнем шаге осталось зайти в настройки репозитория и активировать Github Pages, указав branch gh-pages в качестве источника.

   ![]({{ site.baseurl }}/forestryio/images/github-enable-jekyll.png)

На этом всё. Теперь после каждого коммита Travis CI будет запускать процесс сборки и делать push собранной версий блога в ветку gh-pages. Если перейти на страницу с коммитами на гитхабе, можно увидеть иконку статуса сборки.