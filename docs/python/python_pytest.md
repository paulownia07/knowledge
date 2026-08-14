---
title: pytest
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# [pytest](https://docs.pytest.org/en/stable/)

## import

```
import pytest
```

---

## ディレクトリ構成

```bash
my-project/
├── pyproject.toml
├── README.md
├── .gitignore
├── .venv/
├── src/
│   └── my_package/
│       ├── __init__.py
│       ├── main.py
│       ├── service.py
│       └── utils.py
├── tests/
│   ├── ___init__.py
│   ├── conftest.py
│   ├── test_service.py
│   └── test_utils.py
└── .venv/
```

---

## ルール

- ファイル名は`test_`で始める
- クラス名は`Test`で始める
- 関数名は`test_`で始める

---

## テスト

```Python
# src/service.py

def add(x: int, y:int) -> int:
    return x + y

def subtract(x: int, y:int) -> int:
    return x - y

def multiply(x: int, y:int) -> int:
    return x * y

def divide(x: int, y:int) -> float:
    return x / y
```

```Python
# tests/test_service.py

from my_package.service import add, subtract, multiply, divide

# テストデータ
subtract_testdata = [
    (1, 1, 0),
    (2, 1, 1),
    (1, 2, -1),
    (-1, -2, 1)
    (-2, -1, -1)
]

# add()のテスト関数
def test_add():
    assert add(1, 2) == 3

# subtract()のテスト関数 (複数のパラメータ)
@pytest.mark.parametrize("x,y,expected", subtract_testdata)
def test_subtract(x, y, expected):
    assert subtract(x, y) == expected

# multiply()のテスト関数 (クラス)
class TestMultiply:
    def test_multiply_positive(self):
        assert multiply(3, 3) == 9

    def test_multiply_negative(self):
        assert multiply(3, -3) == -9

    def test_multiply_zero(self):
        assert multiply(3, 0) == 0

# divide()のテスト関数 (例外)
def test_divide_by_zero():
    with pytest.raises(ZeroDivisionError):
        divide(1, 0)
```

---

## mock
本物の処理を偽物に置き換える仕組みであり、主に以下のようなものを置き換える。
- データベース
- Web API
- ファイルアクセス
- メール送信
- 現在時刻
- 環境変数
- 他のクラスや関数

---

## patch
既存のオブジェクトを置き換える仕組み

---

## conftest.py
pytestにおけるテスト共通設定ファイルであり、主に以下のようなものを定義する。

- Fixture
- テスト実行前後の共通処理
- pytestフック
- カスタムマーカー
- テスト用設定

```Python
import pytest

@pytest.fixture
def sample_data():
    return {"name": "test"}
```

---
