---
title: basics
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 2
---

# basics

## PostgreSQL manual

- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [PostgreSQL日本語ドキュメント](https://www.postgresql.jp/document/)

---

## PostgreSQLの起動と停止

1. データベースクラスタを作成する
   ```
   initdb -D /home/postgres/data --no-locale -E UTF8
   ```
2. Postgresサーバを起動する
   ```
   pg_ctl start -D /home/postgres/data -w
   ```
3. Postgresサーバを停止する
   ```
   pg_ctl stop -D /home/postgres/data
   ```

---

## データベースクラスタ

データベースクラスタとはPostgreSQLにおけるデータベースの格納領域であり、実体はファイルシステム上の1つのディレクトリである。

### データベースクラスタの主なディレクトリ構成

```
$PGDATA/               # 上記の /home/postgres/data に対応
├─ PG_VERSION　　　　　 # PostgreSQLのメジャーバージョンを記録するファイル
├─ base/               # 各データベースのサブディレクトリを格納するディレクトリ
│  ├─ 1/
│  ├─ 13948/
│  └─ 13949/
├─ global/             # ユーザ情報などのデータベース間で共有するデータを格納するディレクトリ
├─ log/                # ログファイルを格納するディレクトリ
├─ pg_wal/             # トランザクションログを格納するディレクトリ
├─ postgresql.conf     # PostgreSQLのパラメータを設定するファイル
├─ pg_hba.conf         # クライアントの認証情報を設定するファイル
├─ postmaster.pid      # PostgreSQLサーバのPIDなどを記録するファイル
└─ recovery.signal     # リカバリ時に作成するファイル
```

---

## データベース

データベースとはテーブルなどのデータベースオブジェクトの集合である。データベースの実体は$PGDATA/base/配下の1つのディレクトリと対応しており、ディレクトリ名はデータベースのOIDとなる。

### デフォルトのデータベース

| database    | OID   | description                                    |
| ----------- | ----- | ---------------------------------------------- |
| `template0` | 13948 | 変更不可能なテンプレートデータベース           |
| `template1` | 1     | 変更可能なテンプレートデータベース             |
| `postgres`  | 13949 | デフォルトの接続先として使用されるデータベース |

---

## SQLのコメント

```
-- 単一行コメント
/* 複数行コメント */
```

---

## SQLの記述ルール

- 文の最後は「;」をつける
- キーワードは大文字
- テーブル名の頭文字のみ大文字
- 列名は小文字
- 文字列と日付の定数は「'」(シングルクォーテーション)で囲む。
- 単語の間は半角スペースで区切る
- 評価順序は以下の通り  
  `FROM` → `WHERE` → `GROUP BY` → `HAVING` → `SELECT` → `ORDER BY`

---
