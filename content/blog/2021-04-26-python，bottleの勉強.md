---
title: python，bottleの勉強
slug: study-bottle
date: 2021-04-26T02:42:11.315Z
description: bottleの勉強のメモです。
tags:
  - python
---
## 公式

<https://bottlepy.org/docs/dev/>

>HTTP REQUEST METHODS
>add a method keyword argument to the route() decorator or use one of the five alternative decorators: get(), post(), put(), delete() or patch().

get,post,put,delete,patchが使えるらしい

>ROUTING STATIC FILES
Static files such as images or CSS files are not served automatically. You have to add a route and a callback to control which files get served and where to find them:

from bottle import static_file
@route('/static/<filename>')
def server_static(filename):
    return static_file(filename, root='/path/to/your/static/files')
The static_file() function is a helper to serve files in a safe and convenient way (see Static Files). This example is limited to files directly within the /path/to/your/static/files directory because the <filename> wildcard won’t match a path with a slash in it. To serve files in subdirectories, change the wildcard to use the path filter:

@route('/static/<filepath:path>')
def server_static(filepath):
    return static_file(filepath, root='/path/to/your/static/files')
Be careful when specifying a relative root-path such as root='./static/files'. The working directory (./) and the project directory are not always the same.

## Bottle（pythonフレームワーク）のチュートリアル日本語訳

<https://qiita.com/kouchou/items/5643b1fefde1390f9c63>