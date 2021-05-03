---
title: pythonのormのdatasetの使い方の備忘
slug: study-dataset
date: 2021-05-03T09:34:00.405Z
description: pythonのormのdatasetの使い方の備忘です。
tags:
  - python
---
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


