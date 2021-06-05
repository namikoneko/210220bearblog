---
title: vue loaderの勉強
slug: study-vue-loader
date: 2021-06-05T10:04:03.086Z
description: vue loaderの勉強のメモ
tags:
  - vue
---
公式のcdnを探したが，どうしても見つからなかった

### 参考サイト
<https://votto.net/blog/sfc-without-cli/>

```html
<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/http-vue-loader"></script>
```

```javascript
new Vue({
  el: '#app',
  components: {
    'my-component' httpVueLoader('components/my-component.vue')
  }
})
```

componentsをこんな感じで書く

```html
<div id="app">
  <my-component></my-component>
</div>
```

通常どおりカスタムタグで使える


### 公式ドキュメント
<https://vue-loader.vuejs.org/?#what-is-vue-loader>

```html
<template>
  <div class="example">{{ msg }}</div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Hello world!'
    }
  }
}
</script>

<style>
.example {
  color: red;
}
</style>
```

### github
<https://github.com/vuejs/vue-loader>

サンプルコードがある

<https://github.com/FranckFreiburger/http-vue-loader/blob/master/README.md#more-examples>