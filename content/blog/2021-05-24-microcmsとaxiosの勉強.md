---
title: microcmsとaxiosの勉強
slug: study-microcms-axios
date: 2021-05-24T13:34:41.347Z
description: microcmsとaxiosの勉強です。
tags:
  - vue
---
## コード

```javascript
created(){
axios.get('https://hogehoge.microcms.io/api/v1/my-endpoint',{
headers: {
    'X-API-KEY': '123456789-123456789-123456789'
  }
  })
  .then(res => console.log(res.data.totalCount));
}//created
```

これで，totalCountを表示できた