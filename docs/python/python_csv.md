---
title: csv
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# csv

[csv](https://docs.python.org/ja/3/library/csv.html)はCSV形式のテキストファイルを読み書きするための標準ライブラリ

---

## モジュールの読み込み

```Python
import csv
```

---

## ファイルの操作

### CSVファイルの読み込み

```Python
with open("data/example.csv") as f:
    reader = csv.reader(f)
```

### CSVファイルへの書き込み

```Python
with open("data/example.csv", "w") as f:
    writer = csv.writer(f)
    #単一行の書き込み
    writer.writerow([0, 1, 2])
    #複数行の一括書き込み
    writer.writerows([[1, 2, 3],[4, 5, 6],[7, 8, 9]])
```

---
