---
title: hugoでinkscapeで作ったsvgファイルを表示させる
date: 2021-02-28T10:14:43.172Z
description: hugoをいじっているときに気づいたことのメモです。
tags:
  - hugo
---

参考サイトのコードを、一部改変した

svgファイルは、staticディレクトリに置く

## コード

{{- $src := .Get "src" }}  
{{- $title := .Get "title" }}

{{- /* staticディレクトリのsvgファイルを参照する*/}}  
{{- $svgFile := path.Join ("static/") $src }}

'''
<figure class="xImage">
  <a href="{{ $src }}" target="_blank">
    {{ readFile $svgFile | safeHTML }}
  </a>
  {{- with $title }}
  <figcaption>図: {{ . }}</figcaption>
  {{- end }}
</figure>
'''

## SVGファイルをインラインで埋め込むショートコードを作成する 

<https://maku77.github.io/hugo/shortcode/inline-svg.html>
