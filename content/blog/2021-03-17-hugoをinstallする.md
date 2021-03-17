---
title: hugoをinstallする
slug: hugo-install
date: 2021-03-17T15:04:19.270Z
description: hugoをinstallする方法のメモです。
tags:
  - hugo
---
## 公式
<https://gohugo.io/getting-started/installing/>
>Binary (Cross-platform) 
Download the appropriate version for your platform from Hugo Releases. Once downloaded, the binary can be run from anywhere. You don’t need to install it into a global location. This works well for shared hosts and other systems where you don’t have a privileged account.

>Ideally, you should install it somewhere in your PATH for easy use. /usr/local/bin is the most probable location.


/usr/local/bin が，最も可能性がある置き場所？

>Fedora, Red Hat and CentOS   
>Fedora maintains an official package for Hugo which may be installed with:

`sudo dnf install hugo`

dnfとは？

## UbuntuへHugoをインストール
<https://odaryo.hatenablog.com/entry/2020/06/25/161545>
```
$ wget https://github.com/gohugoio/hugo/releases/download/v0.74.3/hugo_extended_0.74.3_Linux-64bit.deb
```
## メモ
VPSのcentosでhugoを使うことを考えていて，centosにhugoをインストールする方法を調べた。