---
title: pg
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 3
---

# pg

## pg_ctl

| option            | description                  |
| ----------------- | ---------------------------- |
| `-V`, `--version` | ツールのバージョンを表示する |
| `-?`, `--help`    | ツールの使用方法を表示する   |

## pg_ctl start

PostgreSQLをバックグラウンドで起動するためのコマンド

```
pg_ctl start [option]
```

| option                                 | description                                          |
| -------------------------------------- | ---------------------------------------------------- |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する                       |
| `-t` N                                 | 完了までの最大待ち時間をN秒にする (デフォルトは60秒) |

---

## pg_stop

PostgreSQLを停止するためのコマンド

```
pg_ctl stop [option]
```

| option                                 | description                                                                                                                                              |
| -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する                                                                                                                           |
| `-t` N                                 | 完了までの最大待ち時間をN秒にする (デフォルトは60秒)                                                                                                     |
| `-W`                                   | 停止が完了するまで待たない                                                                                                                               |
| `-m` mode                              | 停止方法を指定する<br> `s[mart]`: 接続がすべて切断されてから停止する <br> `f[ast]`: 接続を強制的に切断して停止する <br> `i[mmediate]`: 緊急停止する <br> |

---

## pg_restart

PostgreSQLを再起動するためのコマンド

```
pg_ctl restart [option]
```

| option                                 | description                                                                                                                                              |
| -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する                                                                                                                           |
| `-t` N                                 | 完了までの最大待ち時間をN秒にする (デフォルトは60秒)                                                                                                     |
| `-m` mode                              | 停止方法を指定する<br> `s[mart]`: 接続がすべて切断されてから停止する <br> `f[ast]`: 接続を強制的に切断して停止する <br> `i[mmediate]`: 緊急停止する <br> |

---

## pg_reload

PostgreSQLに設定ファイルを再読み込みさせるためのコマンド

```
pg_ctl reload [option]
```

| option                                 | description                    |
| -------------------------------------- | ------------------------------ |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する |

---

## pg_status

PostgreSQLが起動しているか確認するためのコマンド

```
pg_ctl status [option]
```

| option                                 | description                    |
| -------------------------------------- | ------------------------------ |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する |

---

## pg_kill

プロセスにシグナルを送るためのコマンド

```
pg_ctl kill [sig_name] [PID]
```

| sig_name | description                                                    |
| -------- | -------------------------------------------------------------- |
| `TERM`   | PostgreSQLをスマートシャットダウンする (`pg_stop -m s`と同じ)  |
| `INT`    | PostgreSQLを高速シャットダウンする (`pg_stop -m f`と同じ)      |
| `QUIT`   | PostgreSQLを即時シャットダウンする (`pg_stop -m i`と同じ)      |
| `HUP`    | PostgreSQLに設定ファイルを再読み込みさせる (`pg_reload`と同じ) |

---

## pg_controldata

PostgreSQLデータベースクラスタの制御情報を表示するためのコマンド

```
pg_controldata [option]
```

| option                                 | description                    |
| -------------------------------------- | ------------------------------ |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する |

---

## pg_resetwal

PostgreSQLのWALファイルを消去して制御情報を初期化するためのコマンド

```
pg_resetwal [option]
```

| option                                 | description                    |
| -------------------------------------- | ------------------------------ |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する |

---

## pg_isready

PostgreSQLの接続状態を確認するためのコマンド

```
pg_isready [option]
```

| option                                 | description                    |
| -------------------------------------- | ------------------------------ |
| `-D` db_cluster, `--pgdata=`db_cluster | データベースクラスタを指定する |

---

## pg_config

PostgreSQLのインストール設定情報を確認するためのコマンド

```
pg_config
```

---

## pg_dump

PostgreSQLの???ためのコマンド

```
pg_dump
```

---

## pg_dumpall

PostgreSQLの???ためのコマンド

```
pg_dumpall
```

---

## pg_restore

PostgreSQLの???ためのコマンド

```
pg_restore
```

---

## pg_roles

PostgreSQLの???ためのコマンド

```
pg_roles
```

---

## pg_authid

PostgreSQLの???ためのコマンド

```
pg_authid
```

---
