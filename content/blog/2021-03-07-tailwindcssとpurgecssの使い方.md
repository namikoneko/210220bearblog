---
title: tailwindcssとpurgecssの使い方
slug: tailwindcss-purgecss
date: 2021-03-07T02:45:06.472Z
description: tailwindcssとpurgecssの使い方の個人的なメモです。
tags:
  - css
---
## tailwind.cssの作成（フルのcssファイル）

tailwindcss公式

<https://tailwindcss.com/docs/installation>

>Using Tailwind without PostCSS

>Tailwind CSS requires Node.js 12.13.0 or higher.

>For simple projects or just giving Tailwind a spin, you can use the Tailwind CLI tool to generate your CSS without configuring PostCSS or even installing Tailwind as a dependency if you don't want to.

>Use npx which is a tool that is automatically installed alongside npm to generate a fully compiled Tailwind CSS file:
```
npx tailwindcss-cli@latest build -o tailwind.css
```
### 部分的な大雑把な訳
フルにコンパイルされたTailwind CSS fileを作成（generate）できる

### メモ
この1行だけでできた

npmは入っているのが前提

## purgecssの使い方

purgecss公式

<https://purgecss.com/CLI.html#usage>

>Usage: purgecss --css <css> --content <content> [options]

>Options:  
  -con, --content <files>  glob of content files  
  -css, --css <files>      glob of css files  
  -o, --output <path>      file path directory to write purged css files to

>--output
By default, the CLI outputs the result in the console. If you wish to return the CSS as files, specify the directory to write the purified CSS files to.
```
purgecss --css css/app.css --content src/index.html "src/**/*.js" --output build/css/
```

### メモ
通常、以下の3つのoptionを指定すると思う
* --css（元の大きいtailwindcssのcssファイル）
* --content（htmlファイル）
* --output（不要なcssがremoveされた小さいファイル）

