---
title: Настройка Sublime Text для работы с LaTeX (macOS)
author: serEga
layout: post
permalink: /sublime/sublime-text-latex/
categories: 'Sublime Text'
tags:
  - sublime text
  - latex
amp: true
date: 2016-11-04 17:22:00
---

Перед тем как приступить к написанию и генераций документов с помощью [LaTeX](https://ru.wikipedia.org/wiki/LaTeX) важно выбрать удобный текстовый редактор. Так как в качестве основного редактора я использую [Sublime Text (ST)](https://www.sublimetext.com/3), решил взять его и разобраться с настройками для этой цели.

<a href="{{site.img_cdn}}/sublime-latex.jpg" data-lightbox="sublime-text-latex"><amp-img src="{{site.img_cdn}}/sublime-latex-mini.jpg" alt="Пример с LaTeX файлом в Sublime Text" width="600" height="363"></amp-img></a>

Если вы еще не знакомы с Sublime Text, то рекомендую скачать и попробовать его. Редактор доступен для бесплатного скачивания на официальном сайте.

После установки редактора, перейдем к его настройке для работы с LaTeX. Для этого нам понадобится следующее:

##1. MacTeX
Необходимый пакет для компиляций LaTeX кода (в pdf-файлы). Переходим на сайт [MacTeX](https://tug.org/mactex/), скачиваем и устанавливаем архив.

## 2. LaTeXTools - плагин для ST
LatexTools проще всего установить через [Package Control](https://packagecontrol.io/). Для этого откройте командую строку в Sublime Text и введите команду:

```
import urllib.request,os,hashlib; h = 'df21e130d211cfc94d9b0905775a7c0f' + '1e3d39e33b79698005270310898eea76'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

После этого откройте строку для команд, воспользовавшись комбинацией клавиш Cmd+Shift+P. Поверх редактора откроется всплывающая строка. В нее введем команду "Install Package" и подтвердим с помощью Enter, затем введем название желаемого плагина - [LatexTools](https://github.com/SublimeText/LaTeXTools) и еще раз подтвердим наш выбор. Начнется установка плагина и по её завершению в окне редактора откроется файл с Readme.

## 3.  Skim - просмотрщик pdf-файлов
Для более удобной работы и просмотра скомпилированных pdf-файлов рекомендую установить программу [Skim](http://skim-app.sourceforge.net/).

Теперь когда все готово, можно приступить к верстке документов с помощью LaTeX. Для этого создадим новый файл, например, *first.tex* и поместим в него пару строк текста для пример. Скомпилируем наш код с помощью комбинаций Cmd+B.

Если все было сделано правильно, то в командной строке появиться информация о успешном компилирований файла, а так же автоматический откроется Skim в котором можно увидеть скомпилированный файл. PDF-документ появиться в той же директорий, где был сохранен исходный *.tex-файл.

<a href="{{site.img_cdn}}/latex-compiled-skim.jpg" data-lightbox="sublime-text-latex"><amp-img src="{{site.img_cdn}}/latex-compiled-skim-mini.jpg" alt="Просмотр сгенерированного PDF" width="600" height="278"></amp-img></a>

Для установки дополнительных LaTeX-пакетов можно воспользоваться командой строкой и менеджером пакетов tlmgr. Пример команды для установки пакета *todonotes*:
```
sudo tlmgr install todonotes
``
