---
title: psql
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 4
---

# psql

## psql

PostgreSQLに接続するためのコマンド

```
psql [connect_option]
```

| connect_option                                          | description                             |
| ------------------------------------------------------- | --------------------------------------- |
| `-h` hostname/IP_address, `--host=`host_name/IP_address | 接続先のホスト名/IPアドレスを指定する   |
| `-p` port, `--port=`port                                | ポート番号を指定する (デフォルトは5432) |
| `-U` user_name, `--username=`user_name                  | データベースユーザ名を指定する          |

| option                                       | description                             |
| -------------------------------------------- | --------------------------------------- |
| `-l`, `--list`                               | 接続先のホスト名/IPアドレスを指定する   |
| `-c` command, `--command=`command            | ポート番号を指定する (デフォルトは5432) |
| `-f` file_name, `--file=`file_name           | データベースユーザ名を指定する          |
| `-d` database_name, `--dbname=`database_name |                                         |

## createuser

データベースユーザを作成するためのコマンド

```
createuser [connect_option] [option] user_name
```

| option                  | description                                     |
| ----------------------- | ----------------------------------------------- |
| `-P`, `--pwprompt`      | パスワードを設定する                            |
| `-s`, `-superuser`      | スーパーユーザ権限を設定する                    |
| `-S`, `--no-superuser`  | スーパーユーザ権限を設定しない (デフォルト)     |
| `-d`, `createdb`        | データベースの作成権限を設定する                |
| `-D`, `--no-createdb`   | データベースの作成権限を設定しない (デフォルト) |
| `-r`, `--createrole`    | ユーザの作成権限を設定する                      |
| `-R`, `--no-createrole` | ユーザの作成権限を設定しない (デフォルト)       |
| `-l`, `--login`         | ログイン権限を設定する (デフォルト)             |
| `-L`, `--no-login`      | ログイン権限を設定しない                        |
| `--interactive`         | 対話的に設定する場合に指定する                  |
| `-e`, `--echo`          | createuserが実行したSQlを出力する               |

---

## dropeuser

データベースユーザを削除するためのコマンド

```
dropuser [connect_option] [option] user_name
```

| option                | description      |
| --------------------- | ---------------- |
| `-i`, `--interactive` | 削除前に確認する |

---

## createdb

データベースを作成するためのコマンド

```
createdb [connect_option] [option] database_name
```

| option                                         | description                                |
| ---------------------------------------------- | ------------------------------------------ |
| `-E`, `--encoding=`                            | データベースのエンコーディングを指定する   |
| `-l`, `--locale=`                              | データベースのロケールを指定する           |
| `-O` user_name, `--owner=`user_name            | データベースの所有者となるユーザを指定する |
| `-T` database_name, `--template=`database_name | テンプレートデータベースを指定する         |

---

## dropdb

データベースを削除するためのコマンド

```
dropdb [connect_option] [option] database_name
```

| option                | description      |
| --------------------- | ---------------- |
| `-i`, `--interactive` | 削除前に確認する |

---

## メタコマンド

PostgreSQLに接続した後利用可能なSQL以外のコマンド

| meta command                                 | description                                                                                          |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `\q`, `\quit`                                | psqlを終了する                                                                                       |
| `\l`, `\list`                                | データベース一覧を表示する                                                                           |
| `\d` pattern                                 | 指定したパターンに一致するテーブル、インデックス、ビュー、シーケンスの構成情報を表示する             |
| `\d`                                         | テーブル、インデックス、ビュー、シーケンスの一覧を表示する                                           |
| `\du`                                        | データベースユーザの一覧を表示する                                                                   |
| `\dn`                                        | スキーマの一覧を表示する                                                                             |
| `\dt`                                        | テーブルの一覧を表示する                                                                             |
| `\di`                                        | インデックスの一覧を表示する                                                                         |
| `\dv`                                        | ビューの一覧を表示する                                                                               |
| `\ds`                                        | シーケンスの一覧を表示する                                                                           |
| `\dS`                                        | システムカタログの一覧を表示する                                                                     |
| `\df`                                        | 関数の一覧を表示する                                                                                 |
| `\dp`, `\z`                                  | テーブル、インデックス、ビュー、シーケンスの一覧とそれらに設定されているテーブル単位の権限を表示する |
| `\copy`                                      | PostgreSQlとpsqlの間でテーブルデータをコピーする                                                     |
| `\passward` user_name                        | 指定したユーザのパスワードを変更する (デフォルトは現在のユーザ)                                      |
| `\c` database_name, `\connect` database_name | 指定したデータベースに接続する                                                                       |
| `\x`                                         | 結果の表示形式を拡張モードに変更する                                                                 |
| `\?`                                         | メタコマンドの一覧を表示する                                                                         |
| `\h` SQL, `\help` SQL                        | 指定したSQLコマンドのヘルプ情報を表示する (SQLを指定しない場合はSQLコマンド一覧を表示する)           |

---
