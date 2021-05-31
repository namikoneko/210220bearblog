---
title: vue routerの勉強
slug: study-vuerouter
date: 2021-05-10T14:32:11.394Z
description: vue routerの勉強です。
tags:
  - vue
---
## メモ

`<router-view></router-view>`

の部分を，動的に変えたい場合に，vue routerを使う

vue loaderは，パーツをcomponent化する話として，使い分けるのだと思う

routerのリンク先となるcomponentが複数あるだけなら，scriptタグで別ファイルを読み込めばいいだけである

## 公式

<https://router.vuejs.org/ja/guide/#html>

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

### 動的ルートマッチング

<https://router.vuejs.org/ja/guide/essentials/dynamic-matching.html>

```javascript
  routes: [
    // コロンで始まる動的セグメント
    { path: '/user/:id', component: User }
  ]
})
```


これで /user/foo や /user/bar などの URL 両方とも同じルートにマッチします。



動的セグメントはコロン : を使って表されます。ルートがマッチした時、この動的セグメントの値は全てのコンポーネント内で this.$route.params として利用可能になります。

### 名前付きルート

<https://router.vuejs.org/ja/guide/essentials/named-routes.html>

### ルートコンポーネントにプロパティを渡す（propsの話）

<https://router.vuejs.org/ja/guide/essentials/passing-props.html>

```javascript
const User = {
  props: ['id'],
  template: '<div>User {{ id }}</div>'
}
const router = new VueRouter({
  routes: [
    { path: '/user/:id', component: User, props: true },

    // 名前付きビューによるルートに対しては、名前付きビューごとに `props` オプションを定義しなければなりません:
    {
      path: '/user/:id',
      components: { default: User, sidebar: Sidebar },
      props: { default: true, sidebar: false }
    }
  ]
})
```
