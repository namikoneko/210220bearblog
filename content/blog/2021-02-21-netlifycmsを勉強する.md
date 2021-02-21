---
title: netlifycmsを勉強する
date: 2021-02-21T15:17:31.293Z
description: netlifycmsを勉強したときの記事
tags:
  - diary
  - netlifycms
---
この土日は，netlifycmsを勉強した


previewではまったが，突破できた

hugo用の公式を参考に，netlify.tomlを追加したらできた。

netlifycms公式  
[https://www.netlifycms.org/docs/hugo/](https://www.netlifycms.org/docs/hugo/)

Host on Netlify，netlify.tomlはここを参考にする  
[https://gohugo.io/hosting-and-deployment/hosting-on-netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify)

### tag

以下を参考に`static/admin/config.yml`に以下のように書いてみた  
`- { label: "tags", name: "tags", widget: "list", default: ["diary"] }`

[https://www.netlifycms.org/docs/widgets/#list](https://www.netlifycms.org/docs/widgets/#list)

### body（本文）

サンプルや公式サイトを見ると，本文，`content`の`name`は`body`らしい

`- {label: "Body", name: "body", widget: "markdown"}`

[https://www.netlifycms.org/docs/widgets/#markdown](https://www.netlifycms.org/docs/widgets/#markdown)

### preview

`static/admin/config.yml`の以下の2行をコメントアウトしたらできた

```yml
editor:
preview: false
```

> editor
> This setting changes options for the editor view of a collection or a file inside a files collection. It has one option so far:
> preview: set to false to disable the preview pane for this collection or file; defaults to true

editorには、previewというオプションだけがある

デフォルトはtrueである

falseにセットするとpreview paneがdisableになる

[https://www.netlifycms.org/docs/configuration-options/](https://www.netlifycms.org/docs/configuration-options/)

