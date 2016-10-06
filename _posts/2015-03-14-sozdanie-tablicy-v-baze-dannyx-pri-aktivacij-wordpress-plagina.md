---
id: 8324
title: Создание таблицы в базе данных при активаций WordPress-плагина
date: 2015-03-14T20:45:31+00:00
author: serEga
layout: post
guid: http://artslab.info/?p=8324
permalink: /snippety/sozdanie-tablicy-v-baze-dannyx-pri-aktivacij-wordpress-plagina/
cover:
  - 7841
wpb_post_views_count:
  - 412
dsq_thread_id:
  - 3595196451
categories:
  - snippety
tags:
  - php
  - wordpress
  - сниппет
---
Если при разработке своего плагина для WordPress вы хотите использовать базу данных MySQL, то самый правильный момент для создания необходимой таблицы, это момент активаций плагина. Для этого мы воспользуемся методом _register_activation_hook()_, который зарегистрирует нашу функцию с запросом к базе данных и выполнит ее во время активаций нашего плагина.

Ниже готовый сниппет, который поможет вам выполнить необходимый запрос и создать таблицу со всеми необходимыми полями.

{% highlight php %}

	function create_db_table() {
		global $wpdb;

		// указываем название таблицу
		$table_name = $wpdb->prefix.'event';

		// создаем запрос со всеми наобходимыми полями
		$sql = "CREATE TABLE $table_name (
			id mediumint(9) unsigned NOT NULL AUTO_INCREMENT,
			eventId mediumint(9) NOT NULL,
			authorId mediumint(9) NOT NULL,
			content longtext NOT NULL,
			PRIMARY KEY (id)
		);";

		require_once(ABSPATH.'wp-admin/includes/upgrade.php');

		// выполняем запрос и создаем таблицу
		dbDelta($sql);
	}

	// метод запускающий функцию create_db_table() при активаций плагина
	register_activation_hook(__FILE__, 'create_db_table');

{% endhighlight %}