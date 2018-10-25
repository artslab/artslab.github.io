---
title: Синхронизация настроек VS Code - Settings Sync
date: 2018-10-23 00:00:00 +0000
author: 4gray
layout: post
permalink: "/vscode/sync-vs-code-settings-between-devices"
categories:
- vscode
tags:
- vscode
- editor
amp: true

---
Небольшое, но полезное дополнение под названием [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync&WT.mc_id=vscode-smashing-buhollan) для VS Code позволит без лишних заморочек сохранить и синхронизировать настройки редактора на разных устройствах. Синхронизация работает через сервис сниппетов Github Gist. То есть, при активаций дополнения нужно будет настроить его для работы с этим сервисом, чем мы сейчас и займемся.

<amp-img 
  alt="VS Code Settings Sync - иконка дополнения"
  src="{{ site.baseurl }}/forestryio/images/settings-sync-vscode.jpg" 
  width="128"
  height="128"
  layout="fixed">
  <div fallback>offline</div>
  </amp-img>

1\. Первым делом запускаем редактор, ищем и устанавливаем дополнение [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync&WT.mc_id=vscode-smashing-buhollan), затем перезапускаем VS Code. 2. Теперь переходим на гитхаб, идем в настройки на страничку "[Personal access tokens](https://github.com/settings/tokens)" и генерируем новый токен с разрешением к доступу к gist'ам. на данном этапе важно сохранить токен, как так он понадобиться нам для доступа к файлу конфига на другом устройстве.

<amp-img 
  alt="Настройка токена на гитхаб"
  src="{{ site.baseurl }}/forestryio/images/New personal access token 2018-10-21 17-55-58.jpg" 
  width="759"
  height="658"
  layout="responsive">
  <div fallback>offline</div>
  </amp-img>

3\. Нажимаем Ctrl + Shift + P и в командной строке редактора находим "Sync: Update / Upload Settings", где и нужно будет вставить наш токен. Сразу после этого, дополнение создаст новый Gist с файлами конфигураций и загрузит его на GitHub. Конфиги буду доступны по адресу с таким видом: _https://gist.github.com/{your_userName}/{gist_id}_

Для того чтобы загрузить сохраненную конфигурацию на другом устройстве, необходимо проделать такую же процедуру с токеном, после этого выбирать пункт "Sync: Download Settings" и указать ID gist'a с вашей конфигурацией.

Более [подробный мануал](https://github.com/shanalikhan/code-settings-sync/wiki/Setup-Guide) можно найти на страничке самого дополнения.
