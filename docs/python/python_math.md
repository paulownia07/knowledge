---
title: math
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# math

[math](https://docs.python.org/ja/3/library/math.html)は標準ライブラリとして提供されている数学計算用のツール

---

## モジュールの読み込み

```Python
import math
```

---

## 数学定数

| constant | description       |
| -------- | ----------------- |
| `math.pi`  | 円周率            |
| `math.e`   | ネイピア数        |
| `math.inf` | 正の無限大        |
| `math.nan` | NaN(not a number) |

---

## メソッド

| method                | description                |
| --------------------- | -------------------------- |
| `math.exp(x)`           | eのx乗                     |
| `math.radians(180)`     | 度数法から弧度法への変換   |
| `math.degrees(math.pi)` | 弧度法から度数法への変換   |
| `math.sin(x)`           | サイン                     |
| `math.cos(x)`           | コサイン                   |
| `math.tan(x)`           | タンジェント               |
| `math.asin(x)`          | アークサイン               |
| `math.acos(x)`          | アークコサイン             |
| `math.atan(x)`          | アークタンジェント         |
| `math.sqrt(3)`          | 平方根                     |
| `math.pow(x, y)`        | xのy乗                     |
| `math.log(x\*\*3, x)`   | log(真数、底)              |
| `math.gcd(x, y)`        | 最大公約数                 |
| `math.lcm(x, y)`        | 最小公倍数                 |
| `math.fabs(x)`          | 絶対値                     |
| `math.ceil(x)`          | 切り上げ                   |
| `math.floor(x)`         | 切り下げ                   |
| `math.factorial(x)`     | 階乗                       |
| `math.isclose(x, y)`    | xとyの差が1e-9以内かどうか |

---
