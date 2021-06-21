---
title: python cgiのファイル
slug: python-cgi
date: 2021-06-21T11:50:37.084Z
description: python cgiのファイル
tags:
  - python
---
### index.cgi
```python
#!/usr/local/bin/python
from bottle import route,run,template,request,static_file
import requests,re,calendar

#print "Content-type: text/html\n\n"


@route('/',method='get')
def root():
	#return "root!"
	msg = request.query.msg
	return template('index',msg=msg,url="")

@route('/url',method='get')
def url():
	url = request.query.msg
	f = requests.get(url)
	m = re.search(r'<title>(.*)</title>',f.text,re.IGNORECASE)
	#return "url"
	return template('index',msg=m.group(1),url=url)
```