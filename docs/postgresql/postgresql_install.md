---
title: install
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 1
---

# Install

## Windows

1. [公式サイト](https://www.postgresql.org/)へ移動
2. downloadからOS選択
3. インストールディレクトリの選択 (デフォルトは`C:\Program Files\PostgreSQL\<version>`)
4. データを保存するディレクトリの選択 (デフォルトは`C:\Program Files\PostgreSQL\<version>\data`)
5. 管理者ユーザ(postgres)のパスワードを設定する
6. ポート番号の設定 (デフォルトは`5432`)
7. ロケールを`C`に設定する
8. 環境変数`PATH`に`C:\Program Files\PostgreSQL\<version>\bin`を追加する
9. 設定ファイル(postgresql.conf)を書き換える

---

## Linux (Debian系)

```
sudo apt install -y postgresql postgresql-contrib
```

---
