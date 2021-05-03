---
title: pythonのormのdatasetの使い方の備忘
slug: study-dataset
date: 2021-05-03T09:34:00.405Z
description: pythonのormのdatasetの使い方の備忘です。
tags:
  - python
---
## 公式

<https://dataset.readthedocs.io/en/latest/quickstart.html>

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

### 簡単なコード例

```python
import dataset

db = dataset.connect('sqlite:///test.db')
table = db["test"]#test table

for user in db["test"]:
    print(user["id"])
```

sqliteのファイル、test.db
table、user