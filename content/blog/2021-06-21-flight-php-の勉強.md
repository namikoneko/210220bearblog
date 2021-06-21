---
title: flight(php)の勉強
slug: flight-php-study
date: 2021-06-21T17:02:05.918Z
description: flight(php)の勉強のメモです。
tags:
  - php
---
### 公式サイト

<https://flightphp.com/learn>

```php
Flight::render('header', array('heading' => 'Hello'), 'header_content');
Flight::render('body', array('body' => 'World'), 'body_content');
```
```php
Flight::render('layout', array('title' => 'Home Page'));
```
### header.php:

```php
<h1><?php echo $heading; ?></h1>
```
### body.php:

```php
<div><?php echo $body; ?></div>
```
### layout.php:
```php<html>
<head>
<title><?php echo $title; ?></title>
</head>
<body>
<?php echo $header_content; ?>
<?php echo $body_content; ?>
</body>
</html>

```
### output
```html
<html>
<head>
<title>Home Page</title>
</head>
<body>
<h1>Hello</h1>
<div>World</div>
</body>
</html>
```