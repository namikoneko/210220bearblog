---
title: docker volumeの勉強
slug: study-docker-volume
date: 2021-04-11T13:25:01.312Z
description: docker volumeの勉強です。
tags:
  - docker
---
## dockerコンテナのデータを永続化する方法

<https://tech-blog.rakus.co.jp/entry/20200331/docker>

```
docker run -d --name sample -v my-vol:/app nginx:latest
docker inspect sample
```

-vの次，前がvolume name，後ろが，コンテナ内の共有するディレクトリらしい

```
  "Mounts": [
            {
                "Type": "volume",
                "Name": "my-vol",
                "Source": "/var/lib/docker/volumes/my-vol/_data",//これがホストマシンらしい
                "Destination": "/app",//これがコンテナ内らしい
                "Driver": "local",
                "Mode": "z",
                "RW": true,
                "Propagation": ""
            }
        ],
```

