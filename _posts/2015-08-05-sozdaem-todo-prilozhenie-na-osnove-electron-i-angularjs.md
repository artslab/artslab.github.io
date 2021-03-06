---
id: 8338
title: Создаем ToDo-приложение на основе Electron и AngularJs
date: 2015-08-05 18:03:09 +0000
update_date: 2016-09-26 12:42:00 +0000
author: serEga
layout: post
guid: http://artslab.info/?p=8338
permalink: "/stati/sozdaem-todo-prilozhenie-na-osnove-electron-i-angularjs/"
cover:
- 8345
wpb_post_views_count:
- 2464
dsq_thread_id:
- 4005674254
categories:
- stati
tags:
- angularjs
- electron
- javascript
- material design

---
Давно хотел познакомиться с <a href="https://github.com/atom/electron/" target="_blank">Electron</a>, платформой для создания десктопных приложений на основе веб-технологий, но до этого момента никак не доходили руки. Сегодня мы создадим небольшое ToDo-приложение и используем для этого JavaScript-фреймворк <a href="https://angularjs.org/" target="_blank">AngularJs</a> в связке с гугловским <a href="https://material.angularjs.org" target="_blank">Material Design’ом</a>. Код готового приложения доступен на <a href="https://github.com/4gray/electronTodoApp" target="_blank">Github</a>.

![todo-приложения на основе electron и angularjs]({{ site.baseurl }}/forestryio/images/electron-todo-app-300x234.jpg)

<!--more-->

Первым делом необходимо установить Electron:

<pre>npm install electron-prebuilt -g</pre>

Затем перейдем к созданию самого проекта. Для этого, например, можно воспользоваться <a href="http://yeoman.io/generators/" target="_blank">генератором от Yeoman</a>, либо создать файлы вручную. Так как нам нужно создать всего лишь несколько файлов, мы выберем второй вариант. Создадим новую папку и добавим в нее три файла: app.js, main.js и index.html.

Начнем с первого файла app.js. В нем мы инициализируем наше electron-приложение, укажем опций для окна, название, иконки и прочее. Здесь можно взять за основу код с <a href="https://github.com/atom/electron/blob/master/docs/tutorial/quick-start.md" target="_blank">странички документации</a> и дополнять его по необходимости:

{% highlight javascript %}

    var app = require('app'); // Module to control application life.
    var BrowserWindow = require('browser-window'); // Module to create native browser window.
    
    // Keep a global reference of the window object, if you don't, the window will
    // be closed automatically when the JavaScript object is GCed.
    var mainWindow = null;
    
    // This method will be called when Electron has finished
    // initialization and is ready to create browser windows.
    
    app.on('ready', function() {
      // Create the browser window.
      mainWindow = new BrowserWindow({width: 800, height: 600, resizable: false});
    
      // and load the index.html of the app.
      mainWindow.loadUrl('file://' + __dirname + '/index.html');
    
      // Open the devtools.
      mainWindow.openDevTools();
    
      // Emitted when the window is closed.
      mainWindow.on('closed', function() {
        // Dereference the window object, usually you would store windows
        // in an array if your app supports multi windows, this is the time
        // when you should delete the corresponding element.
        mainWindow = null;
      });
    });

{% endhighlight %}

Теперь создадим index.html в котором будет находиться внешний вид нашего приложения. Для начала просто поместим в него строку текста “Hello world” и для проверки запустим наше приложение с помощью команды:

<pre>electron app.js</pre>

![первый старт приложения]({{ site.baseurl }}/forestryio/images/electron-todo-prilozhenie-start-300x234.jpg) 

Теперь скачаем необходимые нам библиотеки – AngularJs, Angular Material, а так же веб-шрифт с иконками <a href="https://www.google.com/design/icons/" target="_blank">Material Icons</a>. Для этого можем воспользоваться менеджером пакетов npm:

<pre>npm install angular
npm install angular-material</pre>

После того как пакеты скачались их необходимо подключить в index.html. Для работы Angular Material потребуются еще две библиотеки Anuglar Animate и Angular Aria, если скачиваете скрипты вручную, то не забудьте и о этих скриптах.

Сразу же займемся и интерфейсом нашего приложения: добавим тулбар в шапку, боковое меню, а так же список с чекбоксами, которые и будут отображать наши будущие задачи в центральной части приложения. Воспользовавшись заготовками и инструкциями с документации Angular Material, у меня получился такой код:

{% highlight html %}

<!DOCTYPE html>
<html ng-app="todoApp">
<head>
<title>My Todo App</title>
<link rel="stylesheet" type="text/css" href="node_modules/angular-material/angular-material.min.css">

<!-- Web Font with Material Icons -->
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">

<script type="text/javascript" src="node_modules/angular/angular.min.js"></script>
<script type="text/javascript" src="node_modules/angular-animate/angular-animate.min.js"></script>
<script type="text/javascript" src="node_modules/angular-aria/angular-aria.min.js"></script>
<script type="text/javascript" src="node_modules/angular-material/angular-material.min.js"></script>
<script type="text/javascript" src="main.js"></script>

</head>

<body layout="column" ng-controller="AppCtrl" style="background: #eee">

    <!-- Toolbar with title -->
    <md-toolbar layout="row">
      <h1 class="md-toolbar-tools">{{options.name}} &#8211; {{options.show}}</h1>
    </md-toolbar>
    
    <div layout="row" flex>
    
    <!-- Sidebar with navigation -->
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
    
        <!-- all tasks -->
    
        <md-card flex-gt-sm="90" flex-gt-md="80" ng-repeat="task in myTasks | orderBy: &#8216;done&#8217;" ng-if="options.show === &#8216;All tasks&#8217;">
          <md-card-content>
            <md-checkbox aria-label="{{task.title}}" ng-model="task.done">
              <span ng-if="task.done === true" style="text-decoration:line-through; display:block">{{task.title}}</span>
              <span ng-if="task.done === false">{{task.title}}</span>
            </md-checkbox>
          </md-card-content>
        </md-card>
    
        <!-- todo -->
    
        <md-card flex-gt-sm="90" flex-gt-md="80" ng-repeat="task in myTasks | filter: { done: false }" ng-if="options.show === &#8216;Todo&#8217;">
          <md-card-content>
            <md-checkbox aria-label="{{task.title}}" ng-model="task.done">
            {{task.title}}
            </md-checkbox>
          </md-card-content>
        </md-card>
    
        <!-- done tasks -->
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

{% endhighlight %}

Теперь перейдем к основной части нашего списка дел к javascript-логике и для этого откроем третий файл main.js. Здесь мы для начала инициализируем angular-приложение todoApp с модулем ngMaterial, создадим контроллер AppCtrl и инициализируем несколько массивов с объектами. В первый из них поместим три объекта для навигаций с двумя полями: название пункта меню и текстовое название иконки (<a href="https://www.google.com/design/icons/" target="_blank">список всех иконок Material Icons</a>). Во втором массиве мы будем хранить наши задачи и для этого нам так же потребуется два поля: название задачи и статус (сделано или нет). В итоге у меня получилось так:

{% highlight javascript %}

    var app = angular.module('todoApp', ['ngMaterial']);
    app.controller('AppCtrl', ['$scope', function($scope){
      $scope.options = {
        name: 'My Todo List',
        show: 'All tasks'
      };
    
      $scope.navigationBarItems = [
        {'title': 'All tasks', 'icon': 'list'},
        {'title': 'Todo', 'icon': 'assignment'},
        {'title': 'Done', 'icon': 'done'}
      ];
    
      $scope.myTasks = [
        {'title': 'Learn AngularJs', 'done': false},
        {'title': 'Create first app with Electron', 'done': true}
      ];
    
      $scope.setContent = function (content) {
        $scope.options.show = content;
      };
    }]);

{% endhighlight %}

Запустим наше приложением и посмотрим, как оно выглядит и что оно уже умеет.

<pre>electron app.js</pre>

![создание приложение на основе electron]({{ site.baseurl }}/forestryio/images/electro-pervoe-prilozhenie-300x234.jpg) 

На данный момент у нас отображаются все три пункта меню с иконками и две задачи, которые мы поместили в наш массив. Кроме того, мы можем переключаться между тремя созданными списками (все задачи, предстоящий и сделанные).

Теперь предлагаю перейти к созданию формы с помощью которой мы смогли бы добавлять новые задачи в наш список. Для этого я предлагаю добавить Fab-кнопкочку в левый нижний угол приложения, по нажатию на которую у нас бы открывалось popup-окошко с текстовым полем для ввода названия новой задачи.

Для этого добавим код Fab-кнопки в index.html:

{% highlight javascript %}

<md-button class="md-fab md-fab-bottom-right" aria-label="Add" ng-click="showAdd($event)">
<md-icon md-font-set="material-icons">add</md-icon>
</md-button>

{% endhighlight %}

Вернемся к файлу main.js и первым делом пропишем две необходимые нам зависимости $mdDialog и $mdToast для всплывающих оповещений:

{% highlight javascript %}

app.controller('AppCtrl', \['$scope', '$mdDialog', '$mdToast', function($scope, $mdDialog, $mdToast) {…}

{% endhighlight %}

Теперь создадим новую функцию, которая будет открывать новый диалог по нажатию на fab-кнопку:

{% highlight javascript %}

$scope.showAdd = function(ev) {
$mdDialog.show({
controller: AddDialogCtrl,
template: '<md-dialog aria-label="User Form"> <md-content class="md-padding"> <form name="userForm"> <md-input-container> <label>New Task</label> <input ng-model="newTask" placeholder="Placeholder text"> </md-input-container> </form> </md-content> <div class="md-actions" layout="row"> <span flex></span> <md-button ng-click="cancel()"> Cancel </md-button> <md-button ng-click="add(newTask)" class="md-primary"> Add task </md-button> </div></md-dialog>',
targetEvent: ev,
})
.then(function(task) {
$scope.addTask(task);
$mdToast.showSimple('Task “' + task + '” was added!');
});
};

{% endhighlight %}

Как видите, функция show от $mdDialog принимает html-шаблон с диалогом, а так же новый контроллер, который мы сейчас и создадим:

{% highlight javascript %}

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

}

{% endhighlight %}

И конечно же, не забываем добавить функцию addTask(), которая будет добавлять нашу новую задачу в общий массив на первую позицию:

{% highlight javascript %}

$scope.addTask = function (task) {
$scope.myTasks.unshift({
'title': task,
'done': false
});
};

{% endhighlight %}

![todo-app - добавить новую задачу]({{ site.baseurl }}/forestryio/images/electron-dobavit-novuju-zadachu-300x234.jpg) 

В итоге, у меня main.js выглядит следующим образом:

{% highlight javascript %}

var app = angular.module('todoApp', \['ngMaterial'\]);
app.controller('AppCtrl', \['$scope', '$mdDialog', '$mdToast', function($scope, $mdDialog, $mdToast){

    $scope.options = {
      name: 'My Todo List',
      show: 'All tasks'
    };
    
    $scope.navigationBarItems = [
      {'title’: 'All tasks', 'icon': 'list'},
      {'title’: 'Todo', 'icon': 'assignment'},
      {'title': 'Done', 'icon': 'done'}
    ];
    
    $scope.myTasks = [
      {'title': 'Learn AngularJs', 'done': false},
      {'title': 'Create first app with Electron', 'done': true}
    ];
    
    $scope.setContent = function (content) {
      $scope.options.show = content;
    };
    
    $scope.addTask = function (task) {
      $scope.myTasks.unshift({
        'title': task,
        'done': false
      });
    };
    
    $scope.showAdd = function(ev) {
      $mdDialog.show({
        controller: AddDialogCtrl,
        template: '<md-dialog aria-label="User Form"> <md-content class="md-padding"> <form name="userForm"> <md-input-container> <label>New Task</label> <input ng-model="newTask" placeholder="Placeholder text"> </md-input-container> </form> </md-content> <div class="md-actions" layout="row"> <span flex></span> <md-button ng-click="cancel()"> Cancel </md-button> <md-button ng-click="add(newTask)" class="md-primary"> Add task </md-button> </div></md-dialog>',
        targetEvent: ev,
      })
      .then(function(task) {
        $scope.addTask(task);
        $mdToast.showSimple('Task “' + task + '” was added!');
      });
    };

}\]);
function AddDialogCtrl($scope, $mdDialog) {
$scope.hide = function() {
$mdDialog.hide();
};

      $scope.cancel = function() {
        $mdDialog.cancel();
      };
    
      $scope.add = function(task) {
        $mdDialog.hide(task);
      }

}

{% endhighlight %}

![создание приложения на основе electron]({{ site.baseurl }}/forestryio/images/electron-todo-app-300x234.jpg)

На этом пока что все, экспериментируй, расширяйте возможности 🙂 Для сохранения списка дел, например, можно воспользоваться local storage (модуль ngStorage). Весь код данного приложения доступен на [github](https://github.com/4gray/electronTodoApp).

PS: Пишите отзывы, комментируйте непонятные места и задавайте вопросы в комментариях. Буду рад помочь! 😉