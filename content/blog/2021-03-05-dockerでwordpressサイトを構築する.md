---
title: dockerでwordpressサイトを構築する
slug: docker-wordpress
date: 2021-03-05T12:43:15.086Z
description: dockerでwordpressサイトを構築する方法の個人的メモです。
tags:
  - docker
  - wordpress
---
## Quickstart: Compose and WordPress
<https://docs.docker.com/compose/wordpress/>

英語の公式

>Bring up WordPress in a web browser  
At this point, WordPress should be running on port 8000 of your Docker Host

### 意訳

ホストマシンのport8000でアクセスできるらしい。

## 参考site

<https://briarpatch.co.jp/wordpress-docker#toc11>

## メモ

210412, play with dockerで試した

docker-compose.ymlのversionを3.3に変更しろ，とエラーメッセージが出た

そのとおりに変更したら，できた