---
title: Click
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# Click

[Click](https://click.palletsprojects.com/en/stable/)はコマンドラインインターフェース作成キット

---

## モジュールの読み込み

```python
import click
```

---

## 関数の作成

```python
# hello.py
@click.command()
@click.option('--count', default=1, help='Number of greetings.')
@click.option('--name', prompt='Your name',
              help='The person to greet.')
def hello(count, name):
    """Simple program that greets NAME for a total of COUNT times."""
    for x in range(count):
        click.echo(f"Hello {name}!")

if __name__ == '__main__':
    hello()
```

---

## 関数の呼び出し

```bash
python hello.py --count 3 --name John
```

---

## ヘルプを表示する

```bash
python hello.py --help
```

---
