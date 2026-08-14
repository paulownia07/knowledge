---
title: uv
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# uv

[uv](https://docs.astral.sh/uv/)とは、Astral社がRustで開発した超高速な次世代パッケージ兼プロジェクト管理ツール

## import

```Python
import uv
```

---

## project.toml

```toml
[project]
name = "myapp"
version = "0.1.0"
description = "Sample application"
readme = "README.md"
requires-python = ">=3.12"

dependencies = [
    "requests>=2.32.0",
    "pandas>=2.3.0",
]
```

---

## ライブラリの追加

以下のコードを実行すると`project.toml`が自動的に更新される

```bash
uv add pandas
```

---

## 依存関係のインストール

```bash
uv sync
```

---

## ファイルの実行

```bash
uv run python main.py
```

---
