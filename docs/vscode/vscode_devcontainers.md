---
title: Dev Containers
parent: VSCode
layout: default
nav_enabled: true
nav_order: 5
---

# Dev Containers

[Developing inside a Container](https://code.visualstudio.com/docs/devcontainers/containers)

---

## 公式イメージ

[Development Containers Images](https://github.com/devcontainers/images/tree/main/src)

---

## 前提条件

Windows

- WSL: Ubuntu 26.04
- VSCode: Dev Containers拡張機能 (pre-release)
- WSL (3.0以上)

---

## settings.json (ユーザ設定)

```json
{
    "dev.containers.dockerPath": "wslc"
}
```

---

## ファイル構成

```
project-name/
├─ .devcontainer/
│  ├─ devcontainer.json
│  └─ Dockerfile
├─ src/
└─ docs/
```

---
