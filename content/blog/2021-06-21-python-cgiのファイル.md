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
### views/index.html
```html
<!doctype html>
<html lang="ja">
<!--nobanner-->
<head>
	<meta charset="utf-8">
<link rel="icon" type="image/png" href="static/favicon.png">
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
<link rel="stylesheet" href="static/style.css">
<script>
  function myEvent(){
    let range = document.createRange();
    let span = document.getElementById('copy');
    range.selectNodeContents(span);

    let selection = document.getSelection();
    selection.removeAllRanges();
    selection.addRange(range);

    document.execCommand('copy');
    //alert('copied!');
  }
</script>
</head>
<body>
  <div class="container">
		<div class="myoutline text-right">
			<form class="" action="/190429/index.cgi/url" method="get">
			<input type="text" name="msg">
			<input type="submit" value="send">
			</form>
      <div id="copy">
        {{ msg }}
        <br>
        {{ url }}
		  </div>
      <button onclick="myEvent();">copy</button>
		</div>

    <div class="banner">
      <script type="text/javascript" src="https://cache1.value-domain.com/xa.j?site=yaguchineko.s1006.xrea.com"></script>
    </div>
  </div>
</body>
</html>
```