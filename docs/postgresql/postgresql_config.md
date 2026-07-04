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
| `search_path`                   | string  |                                                                                  |
| `default_transaction_isolation` | enum    | 分離レベル (`read uncommited`, `read commited`, `repeated read`, `serializable`) |
| `client_encoding`               | string  | エンコーディング                                                                 |
| `log_destination`               |         |                                                                                  |
| `logging_collector`             | boolean | (`off`, `on`)                                                                    |
| `log_directory`                 |         |                                                                                  |
| `log_filename`                  | string  |                                                                                  |
| `log_min_message`               |         |                                                                                  |
| `log_line_perfix`               |         |                                                                                  |
| ``                              |         |                                                                                  |
| ``                              |         |                                                                                  |
| ``                              |         |                                                                                  |

```
# 以下デフォルト設定
listen_addresses = localhost
port = 5432
max_connections = 100
search_path =
default_transaction_isolation = read commited
client_encoding =
log_destination =
logging_collector = off
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

| auth_method     | description |
| --------------- | ----------- |
| `trust`         |             |
| `reject`        |             |
| `md5`           |             |
| `scram-sha-256` |             |
| `passward`      |             |

---
