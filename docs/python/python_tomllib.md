---
title: tomllib
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# tomllib

[tomllib](https://docs.python.org/ja/3/library/tomllib.html)はtomlファイルを扱うためモジュール

---

## モジュールの読み込み

```Python
import tomllib
```

---

## ファイルの操作

### tomllibファイルの読み込み

```Python
with open(file_path, mode="r") as f:
    data = tomllib.load(f)

username = data["default"]["name"]
```

### tomllibファイルへの書き込み

```Python
with open(file_path, mode="w") as f:
    data = tomllib.load(f)
    data["default"]["age"] = 20
    toml.write(data)
```

---
