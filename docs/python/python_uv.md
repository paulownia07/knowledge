---
title: uv
parent: Python
layout: default
nav_enabled: true
nav_order: 2
---

# uv

[uv](https://docs.astral.sh/uv/)とは、Astral社がRustで開発した超高速な次世代パッケージ兼プロジェクト管理ツール

## インストール

```
curl -LsSf https://astral.sh/uv/install.sh | sh
```

---

## pyproject.toml

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

以下のコードを実行すると`pyproject.toml`が更新される

```
uv add pandas
```

---

## プロジェクトの作成

`pyproject.toml`などが自動的に作成される

```
uv init
```

---

## 依存関係のアップデート

`pyproject.toml`の更新を`uv.lock`に反映させる

```
uv lock
```

---

## 依存関係のインストール

`uv.lock`に記録された依存関係をインストールする

```bash
uv sync
```

---

## ファイルの実行

```
uv run python main.py
```

---
