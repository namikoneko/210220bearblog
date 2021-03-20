---
title: hugoでwebsiteを運営する方法の備忘
slug: hugo-website-run
date: 2021-03-20T03:09:18.862Z
description: hugoでwebsiteを運営する方法の個人的な備忘です。
tags:
  - hugo
---
コマンドで、`hugo new content/blog/my-article.md`して記事を作成するのは、手間が大きいと感じている

CMSにする必要がある。

そこで考えたのが、以下である

1. 記事の新規作成には、forestryを使う
1. これをgithubにあげる（連携させる）
1. xserverとgithubを、github actionsでrsyncさせる

【便利】GitHub Actionsを使ってレンタルサーバーにSSHでデプロイする方法 | カフーブログ

<https://kahoo.blog/github-actions-php-deploy/#SSHGitHub>

わかりやすく書いてある