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

### Linuxにソフトウェアをインストールするには？ | クロの思考ノート
<http://note.kurodigi.com/post-0-15/>
>#3 ネットからバイナリファイルをダウンロードする
この方法はソースが公開されていなかったり、ライセンスの問題が絡んでるソフトに多いです。ここではSkypeを例に上げて見てみましょう。
>公式サイトからskype-4.2.0.13.tar.bz2ファイルをダウンロードします。



>これはdebやrpmパッケージじゃないので上記のようなインストール方法ができません。
以下コマンドで解凍して中身を見てみましょう。

>$ tar -jxf skype-4.2.0.13.tar.bz2
中にはこんなバイナリファイルが入ってます。


>これをREADMEファイルの中身を読んで、自分でディレクトリにコピーする作業がインストール作業です。
### [CentOS8] yum を愛するあなたに送る、 dnf 乗り換え講座 | 株式会社ビヨンド
<https://beyondjapan.com/blog/2019/12/centos8-dnf/>
>yum コマンドが廃止になります  
>これはご存じの方ならばやっとかといったところかも知れませんが、 yum コマンドが廃止されます。
パッケージはどうやって管理するんだ、というところが心配になりますが、安心してください。  
ちゃんと後継のパッケージ管理システムがちゃんと用意されています！

>その後継ツールが dnf です。


## UbuntuへHugoをインストール
<https://odaryo.hatenablog.com/entry/2020/06/25/161545>
```
$ wget https://github.com/gohugoio/hugo/releases/download/v0.74.3/hugo_extended_0.74.3_Linux-64bit.deb
```
## メモ
VPSのcentosでhugoを使うことを考えていて，centosにhugoをインストールする方法を調べた。