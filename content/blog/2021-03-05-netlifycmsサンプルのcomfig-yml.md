---
title: netlifycmsのconfig.ymlのサンプル
slug: netlifycms-configyml-sample
date: 2021-03-05T13:24:32.540Z
description: netlifycmsのサンプルのconfig.ymlです。公式ドキュメントのサンプル，公式のサンプルwebサイトのconfig.ymlです。
tags:
  - netlifycms
---
## 現在のconfig.toml

/static/admin/config.yml

```
backend:
  name: git-gateway
  branch: main # Branch to update (optional; defaults to master)
media_folder: static/img
public_folder: /img
collections:
  - name: 'blog'
    label: 'Blog'
    folder: 'content/blog'
    create: true
    slug: '{{year}}-{{month}}-{{day}}-{{slug}}'
    #    editor:
    #      preview: false
    fields:
      - { label: 'Title', name: 'title', widget: 'string' }
      - { label: "slug", name: "slug", widget: "string" }
      - { label: 'Publish Date', name: 'date', widget: 'datetime' }
      - { label: 'Description', name: 'description', widget: 'string' }
      - { label: "tags", name: "tags", widget: "list", default: ["diary"] }
      - { label: 'Body', name: 'body', widget: 'markdown' }

  - label: "Pages"
    name: "pages"
    files:
      - label: "hugo"
        name: "hugo"
        file: "content/hugo.md"
        fields:
          - {label: Title, name: title, widget: string}
          - { label: 'Publish Date', name: 'date', widget: 'datetime' }
          - { label: 'Body', name: 'body', widget: 'markdown' }
```



## netlifycms公式のcollection-types
<https://www.netlifycms.org/docs/collection-types/>
```
collections:
  - label: "Pages"
    name: "pages"
    files:
      - label: "About Page"
        name: "about"
        file: "site/content/about.yml"
        fields:
          - {label: Title, name: title, widget: string}
          - {label: Intro, name: intro, widget: markdown}
          - label: Team
            name: team
            widget: list
            fields:
              - {label: Name, name: name, widget: string}
              - {label: Position, name: position, widget: string}
              - {label: Photo, name: photo, widget: image}
      - label: "Locations Page"
        name: "locations"
        file: "site/content/locations.yml"
        fields:
          - {label: Title, name: title, widget: string}
          - {label: Intro, name: intro, widget: markdown}
          - label: Locations
            name: locations
            widget: list
            fields:
              - {label: Name, name: name, widget: string}
              - {label: Address, name: address, widget: string}
```

## サンプルのconfig.yml
```
backend:
  name: git-gateway

media_folder: "site/static/img" # Folder where user uploaded files should go
public_folder: "img"

collections: # A list of collections the CMS should be able to edit
  - name: "post" # Used in routes, ie.: /admin/collections/:slug/edit
    label: "Post" # Used in the UI, ie.: "New Post"
    folder: "site/content/post" # The path to the folder where the documents are stored
    create: true # Allow users to create new documents in this collection
    fields: # The fields each document in this collection have
      - {label: "Title", name: "title", widget: "string"}
      - {label: "Publish Date", name: "date", widget: "datetime"}
      - {label: "Intro Blurb", name: "description", widget: "text"}
      - {label: "Image", name: "image", widget: "image", required: false}
      - {label: "Body", name: "body", widget: "markdown"}
  - name: "pages"
    label: "Pages"
    files:
      - file: "site/content/_index.md"
        label: "Home Page"
        name: "home"
        fields:
          - {label: Title, name: title, widget: string}
          - {label: Subtitle, name: subtitle, widget: string}
          - {label: Image, name: image, widget: image}
          - {label: "Blurb", name: blurb, widget: object, fields: [
              {label: "Heading", name: "heading", widget: string},
              {label: "Text", name: "text", widget: "text"}]}
          - {label: "Intro", name: intro, widget: object, fields: [
              {label: "Heading", name: "heading", widget: string},
              {label: "Text", name: "text", widget: "text"}]}
          - {label: "Products", name: products, widget: list, fields: [
              {label: "Image", name: "image", widget: "image"},
              {label: "Text", name: "text", widget: "text"}]}
          - {label: "Values", name: "values", widget: "object", fields: [
              {label: "Heading", name: "heading", widget: string},
              {label: "Text", name: "text", widget: "text"}]}
      - file: "site/content/contact/_index.md"
        label: "Contact Page"
        name: "contact"
        fields:
          - {label: Title, name: title, widget: string}
          - {label: Logo, name: logo, widget: image}
          - {label: Body, name: body, widget: markdown}
          - label: Contact Entries
            name: contact_entries
            widget: list
            fields:
              - label: Heading
                name: heading
                widget: string
              - label: Text
                name: text
                widget: text
      - file: "site/content/products/_index.md"
        label: "Products Page"
        name: "products"
        fields:
          - {label: Title, name: title, widget: string}
          - {label: Image, name: image, widget: image}
          - {label: Heading, name: heading, widget: string}
          - {label: Description, name: description, widget: string}
          - {label: Intro, name: intro, widget: object, fields: [{label: Heading, name: heading, widget: string}, {label: Description, name: description, widget: text}, {label: Blurbs, name: blurbs, widget: list, fields: [{label: Image, name: image, widget: image}, {label: Text, name: text, widget: text}]}]}
          - {label: Main, name: main, widget: object, fields: [{label: Heading, name: heading, widget: string}, {label: Description, name: description, widget: text}, {label: Image1, name: image1, widget: object, fields: [{label: Image, name: image, widget: image}, {label: Alt, name: alt, widget: string}]}, {label: Image2, name: image2, widget: object, fields: [{label: Image, name: image, widget: image}, {label: Alt, name: alt, widget: string}]}, {label: Image3, name: image3, widget: object, fields: [{label: Image, name: image, widget: image}, {label: Alt, name: alt, widget: string}]}]}
          - {label: Testimonials, name: testimonials, widget: list, fields: [{label: Quote, name: quote, widget: string}, {label: Author, name: author, widget: string}]}
          - {label: Full_image, name: full_image, widget: image}
          - {label: Pricing, name: pricing, widget: object, fields: [{label: Heading, name: heading, widget: string}, {label: Description, name: description, widget: string}, {label: Plans, name: plans, widget: list, fields: [{label: Plan, name: plan, widget: string}, {label: Price, name: price, widget: string}, {label: Description, name: description, widget: string}, {label: Items, name: items, widget: list}]}]}
      - file: "site/content/values/_index.md"
        label: "Values Page"
        name: "values"
        fields:
          - {label: Title, name: title, widget: string}
          - {label: Image, name: image, widget: image}
          - label: Values
            name: values
            widget: list
            fields:
              - {label: Heading, name: heading, widget: string}
              - {label: Text, name: text, widget: text}
              - {label: Image, name: imageUrl, widget: image}
```

## メモ
`name: "pages"`は，fileを固定で指定していた。

```
    files:
      - file: "site/content/_index.md"
```
つまり，pageの新規作成はできないようだ。

そもそも，folderにfileを入れたら，それはsectionである。

regular pageではない。

## 210306

regularpageを編集できるように，netlifycmsに追加した。

（content直下のhugo.md）