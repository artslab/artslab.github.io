---
id: 7949
title: 'Google Music: Сохранение музыки на внутреннюю память (Android)'
date: 2013-11-23T17:16:42+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=7949
permalink: /prilozheniya-dlya-android/google-music-soxranenie-muzyki-na-vnutrennyuyu-pamyat-android/
cover:
  - 7959
wpb_post_views_count:
  - 4165
dsq_thread_id:
  - 1992112253
categories:
  - prilozheniya-dlya-android
tags:
  - android
---
С недавних пор мой iPhone 3GS отправился на заслуженную пенсию, а на замену ему пришел андроидфон Xiaomi MI2S. Переход на новую для меня платформу, в принципе, прошел безболезненно и я уже привык к системе.

<center>
  <a href="https://cldup.com/D1oGiJe0yl.jpg"><img src="https://cldup.com/74dxyo5MhJ.jpg" alt="xiaomi mi2s" class="aligncenter size-medium" /></a>
</center>

Первым делом я решил разобраться с синхронизаций музыки. Так как вся моя коллекция аудиофайлов находиться в iTunes, а оттуда загружается на Google Music, я решил использовать облачный сервис для этих целей. Приложение <a href="https://play.google.com/store/apps/details?id=com.google.android.music&#038;hl=ru" target="_blank">Google Play Music</a> имеет очень даже симпатичный интерфейс и легко позволяет сохранять музыку на телефон для оффлайн прослушивания.

Но здесь есть одно небольшое «но», сохранив с десяток альбомов на девайс, я заметил, что свободное место на небольшой внутренней памяти существенно сократилось. Просмотрев настройки приложения, я не нашел возможности для сохранения аудиофайлов во внешнюю память. На помощь, конечно же, пришел гугл и <a href="http://forums.androidcentral.com/sprint-galaxy-s-iii-rooting-roms-hacks/304139-how-save-all-google-play-music-external-sd-card.html" target="_blank">форум Androidcentral</a> 🙂

В целом, идея заключается в созданий новой папки во внешней памяти и размещений ярлыка на нее во внутренней памяти, соответственно, в том месте куда сохраняются треки. Для этого нам понадобятся права суперпользователя (root) и программа ROM Toolbox (бесплатной lite версий будет достаточно).

<center>
  <a href="https://cldup.com/quyVAxVQwq.png"><img src="https://cldup.com/D7-TcfXQc1.png" alt="приложение rom toolbox" class="aligncenter size-medium" /></a>
</center>


**Теперь пошагово:**

1. Ставим приложение <a href="https://play.google.com/store/apps/details?id=com.jrummy.liberty.toolbox&#038;hl=ru" target="_blank">ROM Toolbox</a>
2. Перейдем на внешнюю память (external storage / sdcard) и создадим там папку «GoogleMusic», а в ней еще одну папку «files»
3. Нажимаем и держим на папке files. Из появившегося меню, выбираем последний пункт «Create Shortcut»
4. Переходим во внешнюю память в директорию «/data/data/com.google.android.music/» и удаляем папку files, вместе с ней исчезнут все скачанные аудиозаписи. (если не хотите потерять все сохраненные аудиофайлы, то заранее перенесите их)
5. Нажмите кнопочку Create для создания ярлыка.
6. Готово!