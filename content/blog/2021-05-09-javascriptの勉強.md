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

## findメソッド

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
