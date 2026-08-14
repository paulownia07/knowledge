---
title: psycopg
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# Psycopg

[Psycopg](https://www.psycopg.org/docs/index.html)はPostgreSQLへの接続モジュール

---

## モジュールの読み込み

```Python
import psycopg2
```

---

## 接続

```Python
# 接続情報の設定
con_info = {"user":"<user_name>", "password":"<password>", "host":"<host_name>", "dbname":"<db_name>", "port":5432}

# 接続
conn = psycopg2.connect(**con_info)
```

| parameter | description              |
| --------- | ------------------------ |
| `user`      | ユーザ名                 |
| `password`  | パスワード               |
| `host`      | ホスト名                 |
| `dbname`    | データベース名           |
| `port`      | ポート(デフォルトは5432) |

---

## コネクション操作

| method          | description    |
| --------------- | -------------- |
| `conn.cursor()`   | カーソルの取得 |
| `conn.commit()`   | コミット       |
| `conn.rollback()` | ロールバック   |
| `conn.close()`    | クローズ       |

---

## カーソル操作

| method                         | description  |
| ------------------------------ | ------------ |
| `cur.execute(SQL文, オプション)` | SQLの実行    |
| `cur.fetchone()`                 | 1行フェッチ  |
| `cur.fetchall()`                 | 全行フェッチ |
| `cur.close()`                    | クローズ     |

---

## テンプレート

```Python
import psycopg2

con_info = {"user":"db user", "password":"db password", "host":"localhost", "dbname":"sample"}

with psycopg2.connect(**con_info) as con:
    with con.cursor() as cur:
        smt = sql.SQL("SELECT {} FROM {}").format(sql.Identifier("name", "Tabele_name"))
        rows = cur.execute(smt).fetchall()
```

---
