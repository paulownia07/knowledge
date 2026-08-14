---
title: json
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# json

[json](https://docs.python.org/ja/3/library/json.html)はJSON形式のデータとPythonのデータ構造を相互に変換する標準ライブラリ

---

## モジュールの読み込み

```Python
import json
```

---

## ファイルの操作

### JSON形式のファイルを読み込こんで辞書形式へ変換する

```Python
json_open = open('file_name.json', 'r')
json_load = json.load(json_open)
```

### 辞書形式のデータをJSON形式に変換してファイルに書き込む

```Python
with open('./file_name.json', 'w') as f:
  json.dump(sample_dict, f, indent=4)
```

---
