---
title: Докеризация angular-приложений
author: 4gray
layout: post
date: 2019-11-03 11:03
permalink: "/angular/dockerizaciya-angular-prilozhenyi"
categories:
- angular
amp: true
tags: 
- angular
- docker
image: "../images/2019/docker-angular/angular-prilozhenie-docker.png"
---

Средние размеры приложений в виде docker-образа, которые мне приходилось собирать, составляли менее 30 мб. Речь идёт о приложениях небольшого и среднего размера. Конечно же, итоговый размер образа зависит от используемых статических файлов и библиотек. Если Ваш образ сильно превышает этот размер (занимает 200-300 мб), то возможно вы делаете что-то не так и размер можно будет уменьшить.

Главная причина большого размера образов, это папка `node_modules`, которая, как правило, не должна быть включена в финальный образ с собранным приложением, так как именно она занимает его львиную часть. Благодаря процессу сборки и минификаций кода, приложение вместе со всеми необходимыми зависимостями, будут доступны в отдельной папке `dist` в виде нескольких JS файлов и статического контента (assets).

Теперь осталось выбрать веб-сервер для `хостинга` внутри docker контейнера. Для этого отлично подойдёт nginx с образом alpine из-за его минимального размера. Для nginx нужно подготовить отдельный файл (nginx.conf) с конфигурацией.

В конфигурационном файле мы укажем порт, путь к index.html нашего приложению, а так же активируем сжатие gzip. 

nginx.conf: 
```
TODO добавить сервер и евентс
server {
    listen 80;
    server_name  localhost;
 
    root   /usr/share/nginx/html;
    index  index.html index.htm;
    include /etc/nginx/mime.types;
 
    gzip on;
    gzip_min_length 1000;
    gzip_proxied expired no-cache no-store private auth;
    gzip_types text/plain text/css application/json application/javascript application/x-javascript text/xml application/xml application/xml+rss text/javascript;
 
    location / {
      try_files $uri $uri/ /index.html;
    }
  }
```

Добавим файл .dockerignore включающий в себя те папки и файлы которые нам не понадобятся для сборки (для копирования в наш образ).

```
.git
.gitignore
.github
.vscode
.editorconfig
.dockerignore
Dockerfile
package-lock.json
README.md
dist
e2e
node_modules
```

И сам Dockerfile с описанием сборки:

```
# Step 1: Build angular application
FROM node:12-alpine AS base

# switch to new workdir
WORKDIR /app

# set unsafe permissions
RUN npm config set unsafe-perm true

# copy all files
COPY . .

# install dependencies 
RUN npm install

# build application
RUN npm run build

# Step 2: Copy built artifact and serve app with nginx
FROM nginx:stable-alpine
LABEL version="1.0"

# copy nginx config file
COPY nginx.conf /etc/nginx/nginx.conf

# Copy build version of the application to nginx folder
WORKDIR /usr/share/nginx/html

# replace path for your application
COPY --from=base /app/dist/artslabDemo/ .

# expose port 80 and run nginx
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

Для сборки мы используем два разных базовых имиджа - node и nginx. В рамках первого, мы скопируем наш проект в контейнер, устанавим все зависимости и затем собирем наше Angular-приложение. Во втором шаге мы извлечем необходимые нам "артефакты" из первого контейнера во второй. Таким образом мы получим максимально "чистый" контейнер, включающий nginx и наше приложение. 

---

Теперь проверим всю проделанную работу. Для этого сначала соберем наш имидж с помощью команды:

```$ docker build -t my-angular-app .```

<div class="center-image">
    <amp-img src="https://artslab.info/images/2019/docker-angular/razmer-angular-image-docker.png" alt="Готовый docker образ размером в 21.7мб" title="Готовый docker образ размером в 21.7мб" width="850" height="548" layout="responsive"></amp-img>
    <figcaption>Готовый docker образ размером в 21.7мб</figcaption>
</div>

Дождемся завершения и запустим новый контейнер на основе нашего имиджа:

```$ docker run --name=artslab-demo -d -p 80:80 my-angular-app```

С помощью команды `docker ps` проверим статус контейнера.

<div class="center-image">
    <amp-img src="https://artslab.info/images/2019/docker-angular/status-docker-containera.png" alt="Первый запуск и статус контейнера" title="Статус контейнера с приложением" width="850" height="548" layout="responsive"></amp-img>
    <figcaption>Статус контейнера с приложением</figcaption>
</div>

Убедившись что контейнер запустился, можно смело переходить в браузер и открыть страничку [localhost:80](http://localhost:80) с нашим демо приложением. 

<div class="center-image">
    <amp-img src="https://artslab.info/images/2019/docker-angular/angular-prilozhenie-docker.png" alt="Angular приложение в бразуере" title="Angular приложение в бразуере" width="850" height="605" layout="responsive"></amp-img>
    <figcaption>Angular приложение в бразуере (localhost:80)</figcaption>
</div>

[Репозиторий с примером](https://github.com/artslab/artslab-angular-demo)
