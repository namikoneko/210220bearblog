---
title: pythonのormのdatasetの使い方の備忘
slug: study-dataset
date: 2021-05-03T09:34:00.405Z
description: pythonのormのdatasetの使い方の備忘です。
tags:
  - python
---
## ディレクトリとファイル

/Users/takashi/Downloads/python/200907/flaskworks/create.py

## 公式

### quickstart
<https://dataset.readthedocs.io/en/latest/quickstart.html>

### api
<https://dataset.readthedocs.io/en/latest/api.html>

## SQL備忘

### create table

```
create table thread (
id integer primary key autoincrement,
date text,
postid integer,
title text,
text text,
updated text
);
```

## dataset

### 簡単なコード例

```python
import dataset

#dbに接続
db = dataset.connect('sqlite:///test.db')

table = db["thread"]#table thread

for row in db["thread"]:
    print(row["id"])
```

sqliteのファイル、test.db

tableは、thread

idフィールドを表示している

### delete

```
table.delete(id=10)
```
idが10のレコードを削除

### insert

```
data = dict(title='210503test')
table.insert(data)
```

### update

```
data = dict(id=11, title='now updated!')
table.update(data, ['id'])
```

フィールド名と値で、dict(dictionary)を作って、keyとなるフィールドを指定する

上の例だと、idが11のレコードはすべてupdateされる

### あいまい検索

```
table = db['thread'].table
statement = table.select(table.c.title.like('%update%'))
rows = db.query(statement)
```

datasetそのものには、どうやらあいまい検索はないらしい（下記引用部分参照）

1行目、最後になぜ`.table`をつけるのかは、よくわからない

2行目のかっこの中、`table.c.title.like('%update%')`は、cはカラムの意味、`title`はカラム名ではないかと思う  
（公式サイトでは、`title`が`name`になっており、このnameがdatasetの中で機能的な意味があるのか、単なるカラム名なのか、すごく悩んだ）

>The query() method can also be used to access the underlying SQLAlchemy core API, which allows for the programmatic construction of more complex queries:

SQLAlchemy core APIにアクセスして、より複雑なクエリを構築できる

### Running custom SQL queries

複雑なクエリをしたいときは、公式にもあるように、SQLを書いてしまった方がいいと思う

DBのデータ取得で悩んでも仕方がない

```
result = db.query('SELECT country, COUNT(*) c FROM user GROUP BY country')
for row in result:
   print(row['country'], row['c'])
```

### ここからは公式サイトのみを参考にした

### limit

```
results = table.find(country='France', _limit=10)
```

公式サイトの例

### find_one

```
row = table.find_one(country='United States')
```

公式サイトの例

### order_by

```
# sort results by a column 'year'
results = table.find(country='France', order_by='year')
# return all rows sorted by multiple columns (descending by year)
results = table.find(order_by=['country', '-year'])
```

公式サイトの例

複数カラムでのsortもできる

逆順の場合、カラム名にマイナスをつける

### カラム追加

```
# dataset will create "missing" columns any time you insert a dict with an unknown key  
table.insert(dict(name='Jane Doe', age=37, country='France', gender='female'))
```

insert時に，存在しないカラムを指定すると，いつでもカラムを追加できるらしい

### テーブル，カラム，レコードを
```
>>> print(db.tables)
[u'user']
Now, let’s list all columns available in the table user:

>>> print(db['user'].columns)
[u'id', u'country', u'age', u'name', u'gender']
Using len() we can get the total number of rows in a table:

>>> print(len(db['user']))
2
```