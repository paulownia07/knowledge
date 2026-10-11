---
title: configration
parent: Git
layout: default
nav_enabled: true
nav_order: 2
---

# Configration

## .gitconfig

```
[user]
    name = Your Name
    email = your.email@example.com

[core]
    editor = code --wait
    autocrlf = input
    eol = lf
    quotepath = false
    preloadindex = true

[i18n]
    commitEncoding = utf-8
    logOutputEncoding = utf-8

[gui]
    encoding = utf-8

[init]
    defaultBranch = main

[credential]
    helper = manager

[credential "https://xxx.com"]
    username = your.email@example.com
    helper = manager

[http "https://yyy.com"]
    proxy = http://zzz.zzz.zzz.zzz:8080
    sslCAInfo = /path/to/ca-certificate.pem
    helper = manager
```

---
