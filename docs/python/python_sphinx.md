---
title: Sphinx
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# Sphinx

[Sphinx](https://www.sphinx-doc.org/)は、Pythonで書かれたドキュメント生成ツール。reStructuredText形式のソースからHTMLやPDFなどを生成できる。PythonプロジェクトのAPIリファレンスや利用ガイドの作成に使われる。

---

## import

```python
import sphinx
```

---

## ドキュメントプロジェクトの作成

プロジェクトのルートディレクトリで実行し、対話形式の質問に回答する。ソースとビルド成果物を分ける構成にすると管理しやすい。

```bash
sphinx-quickstart docs
```

HTMLを生成する。

```bash
sphinx-build -M html docs/source docs/build
```

生成された`docs/build/html/index.html`をブラウザーで開いて確認する。`sphinx-quickstart`の設定によってソースディレクトリが異なる場合は、コマンドのパスを構成に合わせる。

---

## ドキュメントの構成

- `conf.py`: Sphinxの設定ファイル
- `index.rst`: ドキュメントのトップページ
- `.rst`: reStructuredText形式の各ページ

トップページから他のページに移動できるよう、`index.rst`に目次を定義する。

```rst
.. toctree::
   :maxdepth: 2

   usage
   reference
```

この例では、`usage.rst`と`reference.rst`を目次に含める。

---

## Python APIリファレンスの生成

`conf.py`の`extensions`に`autodoc`を追加する。

```python
extensions = [
    "sphinx.ext.autodoc",
]
```

ページに`automodule`ディレクティブを記述すると、指定したPythonモジュールのdocstringやメンバーをドキュメントに含められる。

```rst
.. automodule:: my_package.example
   :members:
```

ビルド時に対象パッケージをインポートできる必要がある。必要に応じて、パッケージをインストールするか`conf.py`でPythonの検索パスを設定する。

---
