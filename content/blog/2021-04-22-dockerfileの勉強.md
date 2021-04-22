---
title: Dockerfileの勉強
slug: study-dockerfile
date: 2021-04-22T15:01:09.674Z
description: Dockerfileの勉強です。
tags:
  - docker
---
```
FROM centos
RUN yum install -y httpd
CMD ["/usr/sbin/httpd", "-DFOREGROUND"
```

このDockerfileで，httpdの動作確認ができた