---
title: vue routerの勉強
slug: study-vuerouter
date: 2021-05-10T14:32:11.394Z
description: vue routerの勉強です。
tags:
  - vue
---
## 公式

<https://router.vuejs.org/ja/guide/#html>

### 名前付きルート

<https://router.vuejs.org/ja/guide/essentials/named-routes.html>

### html
```html
<script src="https://unpkg.com/vue/dist/vue.js"></script>
<script src="https://unpkg.com/vue-router/dist/vue-router.js"></script>

<div id="app">
  <h1>Hello App!</h1>
  <p>
    <router-link to="/foo">Go to Foo</router-link>
    <router-link to="/bar">Go to Bar</router-link>
  </p>
  <router-view></router-view>
</div>
```

以下のような表示になる

Hello App!

Go to Foo Go to Bar


### javascript

```javascript
//テンプレートのオブジェクト

const Foo = { template: '<div>foo</div>' }
const Bar = { template: '<div>bar</div>' }


//オブジェクトの配列，pathとcomponentの対応づけ



const routes = [
  { path: '/foo', component: Foo },
  { path: '/bar', component: Bar }
]


const router = new VueRouter({
  routes // `routes: routes` の短縮表記
})


const app = new Vue({
  router
}).$mount('#app')

```