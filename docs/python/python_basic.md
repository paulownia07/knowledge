---
title: basics
parent: Python
layout: default
nav_enabled: true
nav_order: 2
---

# basics

## ドキュメント

[Python 3.14.6 ドキュメント](https://docs.python.org/ja/3/)

---

## コメント

```
# 単一行コメント
# コメント
```

```
# 複数行コメント
''' コメント '''
```

---

## 変数

```
# 変数の初期化
num = 100
```

```
# 変数の削除
del num
```

```
# 定数の定義 (変更は可能)
FIXED_VALUE = 10
```

| type      | description          | example               |
| --------- | -------------------- | --------------------- |
| `bool`    | ブール値             | `True`/`False`        |
| `bytes`   | バイナリデータ       | ???                   |
| `int`     | 整数                 | 2                     |
| `float`   | 浮動小数点           | 1.2345                |
| `str`     | 文字列               | "Hello"               |
| `list`    | リスト               | [1, 2, 3, 4, 5]       |
| `tuple`   | タプル               | (1, 2, 3, 4, 5)       |
| `range`   | 指定した範囲の整数列 | [i for i in range(5)] |
| `set`     | 集合                 | {1, 2, 3, 4, 5}       |
| `dict`    | 辞書                 | {1:"a", 2:"b", 3:"c"} |
| `complex` | 複素数               | 1+2j                  |

---

## 関数

| function        | description                                |
| --------------- | ------------------------------------------ |
| `type(x)`       | 変数の型を調べる                           |
| `id(x)`         | 変数のidを調べる                           |
| `len(var_list)` | コレクションの要素数を返す                 |
| `abs(x)`        | 絶対値                                     |
| `sum(num_list)` | 合計値                                     |
| `max(num_list)` | 最大値                                     |
| `min(num_list)` | 最小値                                     |
| `round(x)`      | 整数に丸めた数値                           |
| `round(x, n)`   | 少数点第n以下に丸めた数値(nはマイナスも可) |
| `pow(x, y)`     | xのy乗                                     |
| `divmod(x, y)`  | x÷yの (商 ,剰余) のタプル                  |
| `int(x)`        | 整数に変換する                             |
| `float(x)`      | 浮動小数に変換する                         |
| `str(x)`        | 文字列に変換する                           |
| `bin(x)`        | 2進数に変換する                            |
| `oct(x)`        | 8進数に変換する                            |
| `hex(x)`        | 16進数に変換する                           |

---

## 標準入力

```
# 文字列を入力する
text = input("文字列を入力してください")
```

```
# 単一の整数値を入力する
num = int(input("数値を入力してください"))
```

```
# 1行で複数の整数値を入力する
a, b, c = map(int, input().split())
```

```
# 1行で複数の整数値を入力してリスト化する
num_list = list(map(int, input().split()))
```

---

## 標準出力

```
# 出力 (改行あり)
print(x)
```

```
# 出力 (改行なし)
print(x, end=" ")
```

| option | description |
| ------ | ----------- |
| `seq`  | 区切り文字  |
| `end`  | 終端文字    |

---

## 文字列

```
# 変数への代入
text = "aaa-bbb-ccc"
```

```
# n番目の文字を取り出す
text[n]
```

```
# nからm番目までの文字列を取り出す
text[n:m+1]
```

```
# フォーマット文字列
text = "Hello! {}さん!".format(name)
text = f"Hello! {name}さん!"
```

| method                                         | description                                                       |
| ---------------------------------------------- | ----------------------------------------------------------------- |
| `text.startswith("aaa")`                       | 引数の文字列が前方一致しているかどうか                            |
| `text.endswith("aaa")`                         | 引数の文字列が後方一致しているかどうか                            |
| `text.replace("old", "new", n)`                | n個の"old"を"new"に置換する (nを省略した場合はすべての置換を行う) |
| `text.strip()`                                 | 文字列の前後の空白を除去する                                      |
| `text.rstrip()`                                | 文字列の前の空白を除去する                                        |
| `text.lstrip()`                                | 文字列の後の空白を除去する                                        |
| `text.upper()`                                 | 文字列を大文字に変換した文字列を返す                              |
| `text.lower()`                                 | 文字列を小文字に変換した文字列を返す                              |
| `text.swapcase()`                              | 大文字と小文字を反転させる                                        |
| `text.capitalize()`                            | 先頭文字のみ大文字、その他は小文字に変換させる                    |
| `text.title()`                                 | 単語の先頭を大文字に、その他は小文字に変換する                    |
| `text.isalnum()`                               | すべての文字が英数字かつ1文字以上あるかどうか                     |
| `text.isalpha()`                               | すべての文字が英字かつ1文字以上あるかどうか                       |
| `text.isascii()`                               | すべての文字がASCIIか空文字であるかどうか                         |
| `text.isdecimal()`                             | すべての文字が10進数の数字かつ1文字以上あるかどうか               |
| `text.islower()`                               | すべての文字が小文字かつ1文字以上あるかどうか                     |
| `text.isupper()`                               | すべての文字が大文字かつ1文字以上あるかどうか                     |
| `text.isspace()`                               | すべての文字が空白文字かつ1文字以上あるかどうか                   |
| `text.split("区切り文字")`                     | 文字列を区切り文字で分割してリストで返す                          |
| `text.zfill(m)`                                | 文字列の長さがmになるように0で左詰めした文字列を返す              |
| `text.rjust(n, "_")`                           | 文字列の長さをnとし、左側の空白を「`_`」で埋める                  |
| `text.ljust(n, "_")`                           | 文字列の長さをnとし、右側の空白を「`_`」で埋める                  |
| `text.center(n, "_")`                          | 文字列の長さをnとし、両側の空白を「`_`」で埋める                  |
| `str1.translate(str.maketrans({"old":"new"}))` | oldをnewに変換する(辞書式で複数一括変換可能)                      |
| `str1.find(str2)`                              | 部分文字列が登場する文字の位置を取得する (前方から)               |
| `str1.rfind(str2)`                             | 部分文字列が登場する文字の位置を取得する (後方から)               |
| `str1.count(str2)`                             | 部分文字列の登場回数を取得する                                    |

---

## 繰り返し

```
# リスト内の要素を変数に格納するループ処理
for x in list1:
    pass
```

```
# 指定回数分のループ処理
for x in range(10):
    pass
```

```
# breakとcontinueを含むループ処理
for x in range(0, 10):
    if x == 4:
        continue
    elif x == 7:
        break
```

```
# 辞書のループ処理
for x in dic1.keys():
for x in dic1.values():
for key, value in dic1.items():
```

```
# カウンタありのループ処理(idxはインデックス、valueは値)
for idx, value enumerate(list1):
```

```
# 複数のリストを同時にループ処理
for val1, val2 in zip(list1, list2):
```

```
# while文
while (i < 10):
    i += 1
```

---

## 条件分岐

```
# 条件分岐
if condition1:
    pass
elif condition2:
    pass
else:
    pass
```

```
# 三項演算子 (signが0のときvalueが0、その他のとき1)
value = 0 if sign == 0 else 1
```

---

## 例外処理

| exception class     | description                                            |
| ------------------- | ------------------------------------------------------ |
| `AttributeError`    | 存在しない属性を指定した場合                           |
| `IndexError`        | 存在しない範囲のインデックスを指定した場合             |
| `KeyError`          | 存在しないキーを指定した場合                           |
| `TypeError`         | 不正な型を指定した場合                                 |
| `ValueError`        | 不正な値を指定した場合                                 |
| `ZeroDivisionError` | ゼロ除算した場合                                       |
| `BaseException`     | すべての例外のスーパークラス                           |
| `Exception`         | システム終了以外のすべての組み込み例外のスーパークラス |

```
try:
    # 例外が起こる可能性がある処理
except <exception class>:
    # 処理
except (<exception class 1>, <exception class 2>) as e:
    # 処理
else:
    # 例外が発生しなかったときの処理
finally:
    # 例外の有無に関わらず実行する終了時の処理
```

```
# 例外を投げる
raise <exception object>
```

```
# アサートを使用する (条件式が偽の場合、メッセージを出力して、AssertionErrorを発生させる)
assert condition, "message"
```

---

## モジュール

```
# モジュールの作成 (ファイル名をperson.pyとした場合、モジュール名はpersonとなる)

import sys
import os

class Person():
    # 「from person import *」としたときに呼び出される関数
    __all__ = ["func1", "func2"]

    def func1():
        # 処理
    def func2():
        # 処理

    # モジュールが直接呼び出されたときの処理
    if __name__ = '__main__':
        # args[0]はファイル名、args[1]は第一引数
        args = sys.argv

```

```
# モジュールのインポートその1
from モジュール名 import クラス名/関数名
```

```
# モジュールのインポートその2
import パッケージ名.モジュール名 as 別名
```

---

## パッケージ

パッケージとは複数のモジュールをまとめたもの。**init**.pyをもつディレクトリ。

```
pkg/
  setup.py
  pkg/ (パッケージ)
    __init__.py (パッケージが呼び出されたときの処理を記述しておくためのファイル)
    __main__.py (パッケージをpythonコマンドで実行したときの処理を記述しておくためのファイル)
    app1.py (モジュール)
    app2.py (モジュール)
    subpkg/ (サブパッケージ)
      __init__.py
      subapp1.py
      subapp2.py
```

### pip installで呼び出せるように設定する

1. setup.pyを編集する
2. setup.pyが配置してあるディレクトリに移動する
3. `pip install .`

```
# setup.pyの例
from setuptools import setup, find_packages

setup(
    name="my_library",
    version="0.1.0",
    packages=find_packages(),
    author="Your Name",
    author_email="your.email@example.com",
    description="A sample Python library",
    long_description=open("README.md").read(),
    PYTHON_REQUIRES = ">=3.6"
    INSTALL_REQUIRES = [
        'numpy >=1.20.3',
        'pandas>=1.2.4',
    ]
)
```

### パッケージのパスを通す

```
# パッケージのパスを通す (for Linux)
export PYTHONPATH="/path/to/pkg1:/path/to/pkg2"
```

```
# パッケージのパスを通す (for コマンドプロンプト)
set PYTHONPATH=/path/to/pkg1;/path/to/pkg2
```

```
# パッケージのパスを通す (for PowerShell)
$env:PYTHONPATH=/path/to/pkg1;/path/to/pkg2
```

---
