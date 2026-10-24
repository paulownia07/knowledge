---
title: Style Guide
parent: Python
layout: default
nav_enabled: true
nav_order: 2
---

# Style Guide

## PEP8

[PEP8](https://pep8-ja.readthedocs.io/ja/latest/)はPython公式のコーディング規約

### Linter

| linter   | description |
| -------- | ----------- |
| `flake8` |             |
| `pylint` |             |

### Formatter

| formatter  | description                                             |
| ---------- | ------------------------------------------------------- |
| `black`    | Black流のスタイルへ統一するPEP8を参考にしたフォーマッタ |
| `autopep8` | PEP8違反を自動修正するフォーマッタ                      |
| `YAPF`     | Blackより設定自由度が高いGoogle製のフォーマッタ         |

---

## PEP257

[PEP 257](https://peps.python.org/pep-0257/)は、モジュール・クラス・関数などのDocstringの書き方に関する規約です。Docstringは定義の直後に置く文字列で、`help()`やドキュメント生成ツールから参照できます。引数や戻り値などの詳しい記述形式は、Google styleやNumPy styleなどの規約で定められています。

- 三重ダブルクォート（`"""`）で囲む
- 1行目に対象の概要を簡潔に書く
- 複数行の場合は、概要の後に空行を入れて詳細を書く

| checker      | description                                          |
| ------------ | ---------------------------------------------------- |
| `pydocstyle` | DocstringがPEP 257などの規約に沿っているかを検査する |

### Google style

Google styleは、引数や戻り値などを見出しごとに記述する形式です。型は名前の後に括弧で書きます。

```python
"""このモジュールの説明。"""

class User:
    """ユーザーを表すクラス。"""

    def greet(self, name: str) -> str:
        """名前を指定して挨拶する。

        Args:
            name (str): 挨拶する相手の名前。

        Returns:
            str: 挨拶のメッセージ。
        """
        return f"こんにちは、{name}さん"
```

### NumPy style

NumPy styleは、項目名・型・説明を分けて記述する形式です。`Parameters`や`Returns`の下に区切り線を置きます。

```python
"""このモジュールの説明。"""

class User:
    """ユーザーを表すクラス。"""

    def greet(self, name: str) -> str:
        """名前を指定して挨拶する。

        Parameters
        ----------
        name : str
            挨拶する相手の名前。

        Returns
        -------
        str
            挨拶のメッセージ。
        """
        return f"こんにちは、{name}さん"
```

---

## Ruff

flake8・isort・pydocstyle・blackの多くを代替する統合ツール  
Pythonの新規プロジェクトであれば、特別な理由がなければ 「Ruff + mypy」 を採用しておくと、シンプルかつ高速な構成になる

```toml
# pyproject.toml
[tool.ruff]
target-version = "py311"
line-length = 88
indent-width = 4

exclude = [
    ".git",
    ".venv",
    ".mypy_cache",
    ".pytest_cache",
    "__pycache__",
    "build",
    "dist",
]

[tool.ruff.lint]
select = [
    # pycodestyle
    "E",
    "W",

    # pyflakes
    "F",

    # isort
    "I",

    # pyupgrade
    "UP",

    # flake8-bugbear
    "B",

    # flake8-simplify
    "SIM",

    # pydocstyle
    "D",

    # type annotation
    "ANN",
]

ignore = [
    "D100", # module docstring
    "D104", # package docstring
]

[tool.ruff.lint.pydocstyle]
convention = "google"

[tool.ruff.format]
quote-style = "double"
indent-style = "space"
line-ending = "lf"
docstring-code-format = true
```

---
