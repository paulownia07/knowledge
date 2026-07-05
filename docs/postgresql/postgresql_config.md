---
title: configration
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 3
---

# configration

## postgresql.conf

PostgreSQLのパラメータを設定するためのファイル
`initdb`で作成され、`$PGDATA`ディレクトリに配置される

| config                          | type    | description                                                                      |
| ------------------------------- | ------- | -------------------------------------------------------------------------------- |
| `listen_addresses`              | string  | クライアントからの接続を監視するPostgreSQL側のIPアドレス/ホスト名                |
| `port`                          | integer | クライアントからの接続を受け付けるポート番号                                     |
| `max_connections`               | integer | 同時接続可能な最大数                                                             |
| `search_path`                   | string  | スキーマ検索パス                                                                 |
| `default_transaction_isolation` | enum    | 分離レベル (`read uncommited`, `read commited`, `repeated read`, `serializable`) |
| `client_encoding`               | string  | クライアントエンコーディング (`UTF8`, `EUC_JP`, `SJIS`)                          |
| `log_destination`               | enum    | サーバログの出力先 (`stderr`, `csvlog`, `syslog`, `eventlog`)                    |
| `logging_collector`             | boolean | 標準エラー出力をファイルにリダイレクトするかどうか (`off`, `on`)                 |
| `log_directory`                 | string  | ログファイルを格納するディレクトリ                                               |
| `log_filename`                  | string  | ログファイルの名前                                                               |
| `log_min_message`               | enum    | ログレベルの設定 (`PANIC`, `FATAL`, `LOG`, `ERROR`, `WARNING`)                   |
| `log_line_perfix`               | string  | ログの行頭に出力する内容                                                         |
| `autovacuum`                    | boolean | 自動バキュームを有効化するかどうか (`off`, `on`)                                 |

```
# 以下デフォルト設定
listen_addresses = 'localhost'
port = 5432
max_connections = 100
search_path = "$user", public
default_transaction_isolation = read commited
client_encoding = UTF8
log_destination = stderr
logging_collector = off
log_directory = 'log'
log_filename = 'postgresql-%Y-%m-%d_%H%M%S.log'
log_min_message = WARNING
log_line_perfix = '%m [%p]'
autovacuum = on
```

---

## pg_hba.conf

クライアント認証を設定するファイル  
`initdb`で作成され、`$PGDATA`ディレクトリに配置される

```
# UNIXドメイン接続に対応する
local    <database_name>    <user_name>    auth_method

# TCP/IP接続に対応する
host    <database_name>    <user_name>    <CIDR>    auth_method
```

| auth_method     | description                   |
| --------------- | ----------------------------- |
| `trust`         | 接続を常に許可する            |
| `reject`        | 接続を常に拒否する            |
| `md5`           | パスワード認証を行う          |
| `scram-sha-256` | パスワード認証を行う (推奨)   |
| `passward`      | パスワード認証を行う (非推奨) |

---
