---
title: Python coding standards
parent: Python
layout: default
nav_enabled: true
nav_order: 3
---

# Python coding standards

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

PEP257はDocstringの規約

| checker      | description |
| ------------ | ----------- |
| `pydocstyle` |             |

---

## Ruff

flake8・isort・pydocstyle・blackの多くを代替する統合ツール  
Pythonの新規プロジェクトであれば、特別な理由がなければ 「Ruff + mypy」 を採用しておくと、シンプルかつ高速な構成になる

```
# project.toml
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
