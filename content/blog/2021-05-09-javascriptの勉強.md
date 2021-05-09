---
title: JavaScriptの勉強
slug: study-javascript
date: 2021-05-09T04:48:42.477Z
description: JavaScriptの勉強です。
tags:
  - javascript
---
## 関数

### ごく簡単な例

```javascript
function multiple(num){
    return num * 2;
}
alert(multiple(3));
```

JavaScript Primer,p65

### Arrow Function

```javascript
const multiple = (num) => {
    return num * 2;
}
alert(multiple(3));
```

JavaScript Primer,p73

## メソッド

### findメソッド

特定の要素がほしいときに使う。

```javascript
const colors = [
    {"color": "red"},
    {"color": "green"},
    {"color": "blue"}
];

const blueColor = colors.find((obj) => {//findで，配列のそれぞれをobjに代入する
    return obj.color === "blue";//objのcolorがblueと等しければreturnする
});
console.log(blueColor);
```

JavaScript Primer,p133

### filterメソッド

配列から不要な要素を除いた配列を作成したい場合に使う。

```javascript
const array = [1,2,3];
const newArray = array.filter((currentValue,index,array) => {
    return currentValue % 2 === 1;
});
console.log(newArray);
```

コールバック関数には，要素，インデックス，配列が，引数として渡される。

返り値は，コールバック関数がtrueを返した要素だけを集めた新しい配列

JavaScript Primer,p143