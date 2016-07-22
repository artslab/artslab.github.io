---
id: 8338
title: Создаем ToDo-приложение на основе Electron и AngularJs
date: 2015-08-05T18:03:09+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=8338
permalink: /stati/sozdaem-todo-prilozhenie-na-osnove-electron-i-angularjs/
cover:
  - 8345
wpb_post_views_count:
  - 2464
dsq_thread_id:
  - 4005674254
categories:
  - Статьи
tags:
  - angularjs
  - electron
  - javascript
  - material design
---
<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app-300x234.jpg" alt="todo-приложения на основе electron и angularjs" class="aligncenter size-medium wp-image-8341" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app-300x234.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app-900x702.jpg 900w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app.jpg 912w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Давно хотел познакомиться с <a href="https://github.com/atom/electron/" target="_blank">Electron</a>, платформой для создания десктопных приложений на основе веб-технологий, но до этого момента никак не доходили руки. Сегодня мы создадим небольшое ToDo-приложение и используем для этого JavaScript-фреймворк <a href="https://angularjs.org/" target="_blank">AngularJs</a> в связке с гугловским <a href="https://material.angularjs.org" target="_blank">Material Design’ом</a>. Код готового приложения доступен на <a href="https://github.com/4gray/electronTodoApp" target="_blank">Github</a>.

<!--more-->

Первым делом необходимо установить Electron:

<pre>npm install electron-prebuilt -g</pre>

Затем перейдем к созданию самого проекта. Для этого, например, можно воспользоваться <a href="http://yeoman.io/generators/" target="_blank">генератором от Yeoman</a>, либо создать файлы вручную. Так как нам нужно создать всего лишь несколько файлов, мы выберем второй вариант. Создадим новую папку и добавим в нее три файла: app.js, main.js и index.html.

Начнем с первого файла app.js. В нем мы инициализируем наше electron-приложение, укажем опций для окна, название, иконки и прочее. Здесь можно взять за основу код с <a href="https://github.com/atom/electron/blob/master/docs/tutorial/quick-start.md" target="_blank">странички документации</a> и дополнять его по необходимости:

[js]

var app = require(&#8216;app&#8217;); // Module to control application life.

var BrowserWindow = require(&#8216;browser-window&#8217;); // Module to create native browser window.

// Keep a global reference of the window object, if you don&#8217;t, the window will

// be closed automatically when the JavaScript object is GCed.

var mainWindow = null;

// This method will be called when Electron has finished

// initialization and is ready to create browser windows.

app.on(&#8216;ready&#8217;, function() {

// Create the browser window.

mainWindow = new BrowserWindow({width: 800, height: 600, resizable: false});

// and load the index.html of the app.

mainWindow.loadUrl(&#8216;file://&#8217; + __dirname + &#8216;/index.html&#8217;);

// Open the devtools.

mainWindow.openDevTools();

// Emitted when the window is closed.

mainWindow.on(&#8216;closed&#8217;, function() {

// Dereference the window object, usually you would store windows

// in an array if your app supports multi windows, this is the time

// when you should delete the corresponding element.

mainWindow = null;

});

});

[/js]

Теперь создадим index.html в котором будет находиться внешний вид нашего приложения. Для начала просто поместим в него строку текста &#8220;Hello world&#8221; и для проверки запустим наше приложение с помощью команды:

<pre>electron app.js</pre>

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-prilozhenie-start.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-prilozhenie-start-300x234.jpg" alt="первый старт приложения" width="300" height="234" class="aligncenter size-medium wp-image-8339" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-prilozhenie-start-300x234.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-prilozhenie-start-900x702.jpg 900w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-prilozhenie-start.jpg 912w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

Теперь скачаем необходимые нам библиотеки &#8211; AngularJs, Angular Material, а так же веб-шрифт с иконками <a href="https://www.google.com/design/icons/" target="_blank">Material Icons</a>. Для этого можем воспользоваться менеджером пакетов npm:

<pre>npm install angular
npm install angular-material</pre>

После того как пакеты скачались их необходимо подключить в index.html. Для работы Angular Material потребуются еще две библиотеки Anuglar Animate и Angular Aria, если скачиваете скрипты вручную, то не забудьте и о этих скриптах.

Сразу же займемся и интерфейсом нашего приложения: добавим тулбар в шапку, боковое меню, а так же список с чекбоксами, которые и будут отображать наши будущие задачи в центральной части приложения. Воспользовавшись заготовками и инструкциями с документации Angular Material, у меня получился такой код:

[html]

<!DOCTYPE html>

<html ng-app="todoApp">

<head>

<title>My Todo App</title>

<link rel="stylesheet" type="text/css" href="node_modules/angular-material/angular-material.min.css">

<!&#8211; Web Font with Material Icons &#8211;>

<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">

<script type="text/javascript" src="node_modules/angular/angular.min.js"></script>

<script type="text/javascript" src="node_modules/angular-animate/angular-animate.min.js"></script>

<script type="text/javascript" src="node_modules/angular-aria/angular-aria.min.js"></script>

<script type="text/javascript" src="node_modules/angular-material/angular-material.min.js"></script>

<script type="text/javascript" src="main.js"></script>

</head>

<body layout="column" ng-controller="AppCtrl" style="background: #eee">

<!&#8211; Toolbar with title &#8211;>

<md-toolbar layout="row">

<h1 class="md-toolbar-tools">{{options.name}} &#8211; {{options.show}}</h1>

</md-toolbar>

<div layout="row" flex>

<!&#8211; Sidebar with navigation &#8211;>

<md-sidenav layout="column" class="md-sidenav-left md-whiteframe-z2" md-component-id="left" md-is-locked-open="$mdMedia(&#8216;gt-sm&#8217;)">

<md-content>

<md-list>

<md-list-item ng-repeat="navItem in navigationBarItems" ng-click="setContent(navItem.title)">

<md-icon md-font-set="material-icons">{{navItem.icon}}</md-icon>

<p>{{navItem.title}}</p>

<md-divider></md-divider>

</md-list-item>

</md-list>

</md-content>

</md-sidenav>

<div layout="column" flex id="content">

<!&#8211; all tasks &#8211;>

<md-card flex-gt-sm="90" flex-gt-md="80" ng-repeat="task in myTasks | orderBy: &#8216;done&#8217;" ng-if="options.show === &#8216;All tasks&#8217;">

<md-card-content>

<md-checkbox aria-label="{{task.title}}" ng-model="task.done">

<span ng-if="task.done === true" style="text-decoration:line-through; display:block">{{task.title}}</span>

<span ng-if="task.done === false">{{task.title}}</span>

</md-checkbox>

</md-card-content>

</md-card>

<!&#8211; todo &#8211;>

<md-card flex-gt-sm="90" flex-gt-md="80" ng-repeat="task in myTasks | filter: { done: false }" ng-if="options.show === &#8216;Todo&#8217;">

<md-card-content>

<md-checkbox aria-label="{{task.title}}" ng-model="task.done">

{{task.title}}

</md-checkbox>

</md-card-content>

</md-card>

<!&#8211; done tasks &#8211;>

<md-card flex-gt-sm="90" flex-gt-md="80" ng-repeat="task in myTasks | filter: { done: true }" ng-if="options.show === &#8216;Done&#8217;">

<md-card-content>

<md-checkbox aria-label="{{task.title}}" ng-model="task.done">

<span style="text-decoration:line-through; display:block">{{task.title}}</span>

</md-checkbox>

</md-card-content>

</md-card>

</div>

</div>

</body>

</html>

[/html]

Теперь перейдем к основной части нашего списка дел к javascript-логике и для этого откроем третий файл main.js. Здесь мы для начала инициализируем angular-приложение todoApp с модулем ngMaterial, создадим контроллер AppCtrl и инициализируем несколько массивов с объектами. В первый из них поместим три объекта для навигаций с двумя полями: название пункта меню и текстовое название иконки (<a href="https://www.google.com/design/icons/" target="_blank">список всех иконок Material Icons</a>). Во втором массиве мы будем хранить наши задачи и для этого нам так же потребуется два поля: название задачи и статус (сделано или нет). В итоге у меня получилось так:

[js]

var app = angular.module(&#8216;todoApp&#8217;, [&#8216;ngMaterial&#8217;]);

app.controller(&#8216;AppCtrl&#8217;, [&#8216;$scope&#8217;, function($scope){

$scope.options = {

name: &#8216;My Todo List&#8217;,

show: &#8216;All tasks&#8217;

};

$scope.navigationBarItems = [

{&#8216;title&#8217;: &#8216;All tasks&#8217;, &#8216;icon&#8217;: &#8216;list&#8217;},

{&#8216;title&#8217;: &#8216;Todo&#8217;, &#8216;icon&#8217;: &#8216;assignment&#8217;},

{&#8216;title&#8217;: &#8216;Done&#8217;, &#8216;icon&#8217;: &#8216;done&#8217;}

];

$scope.myTasks = [

{&#8216;title&#8217;: &#8216;Learn AngularJs&#8217;, &#8216;done&#8217;: false},

{&#8216;title&#8217;: &#8216;Create first app with Electron&#8217;, &#8216;done&#8217;: true}

];

$scope.setContent = function (content) {

$scope.options.show = content;

};

}]);

[/js]

Запустим наше приложением и посмотрим, как оно выглядит и что оно уже умеет.

<pre>electron app.js</pre>

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electro-pervoe-prilozhenie.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electro-pervoe-prilozhenie-300x234.jpg" alt="создание приложение на основе electron" class="aligncenter size-medium wp-image-8343" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electro-pervoe-prilozhenie-300x234.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electro-pervoe-prilozhenie-900x702.jpg 900w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electro-pervoe-prilozhenie.jpg 912w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

На данный момент у нас отображаются все три пункта меню с иконками и две задачи, которые мы поместили в наш массив. Кроме того, мы можем переключаться между тремя созданными списками (все задачи, предстоящий и сделанные).

Теперь предлагаю перейти к созданию формы с помощью которой мы смогли бы добавлять новые задачи в наш список. Для этого я предлагаю добавить Fab-кнопкочку в левый нижний угол приложения, по нажатию на которую у нас бы открывалось popup-окошко с текстовым полем для ввода названия новой задачи.

Для этого добавим код Fab-кнопки в index.html:

[html]

<md-button class="md-fab md-fab-bottom-right" aria-label="Add" ng-click="showAdd($event)">

<md-icon md-font-set="material-icons">add</md-icon>

</md-button>

[/html]

Вернемся к файлу main.js и первым делом пропишем две необходимые нам зависимости $mdDialog и $mdToast для всплывающих оповещений:

[js]

app.controller(&#8216;AppCtrl&#8217;, [&#8216;$scope&#8217;, &#8216;$mdDialog&#8217;, &#8216;$mdToast&#8217;, function($scope, $mdDialog, $mdToast) {&#8230;}

[/js]

Теперь создадим новую функцию, которая будет открывать новый диалог по нажатию на fab-кнопку:

[js]

$scope.showAdd = function(ev) {

$mdDialog.show({

controller: AddDialogCtrl,

template: &#8216;<md-dialog aria-label="User Form"> <md-content class="md-padding"> <form name="userForm"> <md-input-container> <label>New Task</label> <input ng-model="newTask" placeholder="Placeholder text"> </md-input-container> </form> </md-content> <div class="md-actions" layout="row"> <span flex></span> <md-button ng-click="cancel()"> Cancel </md-button> <md-button ng-click="add(newTask)" class="md-primary"> Add task </md-button> </div></md-dialog>&#8217;,

targetEvent: ev,

})

.then(function(task) {

$scope.addTask(task);

$mdToast.showSimple(&#8216;Task "&#8217; + task + &#8216;" was added!&#8217;);

});

};

[/js]

Как видите, функция show от $mdDialog принимает html-шаблон с диалогом, а так же новый контроллер, который мы сейчас и создадим:

[js]

function AddDialogCtrl($scope, $mdDialog) {

$scope.hide = function() {

$mdDialog.hide();

};

$scope.cancel = function() {

$mdDialog.cancel();

};

$scope.add = function(task) {

$mdDialog.hide(task);

};

};

[/js]

И конечно же, не забываем добавить функцию addTask(), которая будет добавлять нашу новую задачу в общий массив на первую позицию:

[js]

$scope.addTask = function (task) {

$scope.myTasks.unshift({

&#8216;title&#8217;: task,

&#8216;done&#8217;: false

});

};

[/js]

<center>
  <a href="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-dobavit-novuju-zadachu.jpg"><img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-dobavit-novuju-zadachu-300x234.jpg" alt="todo-app - добавить новую задачу" class="aligncenter size-medium wp-image-8340" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-dobavit-novuju-zadachu-300x234.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-dobavit-novuju-zadachu-900x702.jpg 900w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-dobavit-novuju-zadachu.jpg 912w" sizes="(max-width: 300px) 100vw, 300px" /></a>
</center>

В итоге, у меня main.js выглядит следующим образом:

[js]

var app = angular.module(&#8216;todoApp&#8217;, [&#8216;ngMaterial&#8217;]);

app.controller(&#8216;AppCtrl&#8217;, [&#8216;$scope&#8217;, &#8216;$mdDialog&#8217;, &#8216;$mdToast&#8217;, function($scope, $mdDialog, $mdToast){

$scope.options = {

name: &#8216;My Todo List&#8217;,

show: &#8216;All tasks&#8217;

};

$scope.navigationBarItems = [

{&#8216;title&#8217;: &#8216;All tasks&#8217;, &#8216;icon&#8217;: &#8216;list&#8217;},

{&#8216;title&#8217;: &#8216;Todo&#8217;, &#8216;icon&#8217;: &#8216;assignment&#8217;},

{&#8216;title&#8217;: &#8216;Done&#8217;, &#8216;icon&#8217;: &#8216;done&#8217;}

];

$scope.myTasks = [

{&#8216;title&#8217;: &#8216;Learn AngularJs&#8217;, &#8216;done&#8217;: false},

{&#8216;title&#8217;: &#8216;Create first app with Electron&#8217;, &#8216;done&#8217;: true}

];

$scope.setContent = function (content) {

$scope.options.show = content;

};

$scope.addTask = function (task) {

$scope.myTasks.unshift({

&#8216;title&#8217;: task,

&#8216;done&#8217;: false

});

};

$scope.showAdd = function(ev) {

$mdDialog.show({

controller: AddDialogCtrl,

template: &#8216;<md-dialog aria-label="User Form"> <md-content class="md-padding"> <form name="userForm"> <md-input-container> <label>New Task</label> <input ng-model="newTask" placeholder="Placeholder text"> </md-input-container> </form> </md-content> <div class="md-actions" layout="row"> <span flex></span> <md-button ng-click="cancel()"> Cancel </md-button> <md-button ng-click="add(newTask)" class="md-primary"> Add task </md-button> </div></md-dialog>&#8217;,

targetEvent: ev,

})

.then(function(task) {

$scope.addTask(task);

$mdToast.showSimple(&#8216;Task "&#8217; + task + &#8216;" was added!&#8217;);

});

};

}]);

function AddDialogCtrl($scope, $mdDialog) {

$scope.hide = function() {

$mdDialog.hide();

};

$scope.cancel = function() {

$mdDialog.cancel();

};

$scope.add = function(task) {

$mdDialog.hide(task);

};

};

[/js]

[<img src="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app-300x234.jpg" alt="создание приложения на основе electron" class="aligncenter size-medium wp-image-8341" srcset="http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app-300x234.jpg 300w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app-900x702.jpg 900w, http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app.jpg 912w" sizes="(max-width: 300px) 100vw, 300px" />](http://googledrive.com/host/0B9lHVSSSdxdxd0hjdUdmRzY3Tjg/electron-todo-app.jpg)

На этом пока что все, экспериментируй, расширяйте возможности 🙂 Для сохранения списка дел, например, можно воспользоваться local storage (модуль ngStorage). Весь код данного приложения доступен на [github](https://github.com/4gray/electronTodoApp).

PS: Пишите отзывы, комментируйте непонятные места и задавайте вопросы в комментариях. Буду рад помочь! 😉