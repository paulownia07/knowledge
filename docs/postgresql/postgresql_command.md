---
title: command
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 4
---

# command

## command manual

- [SQLコマンド](https://www.postgresql.jp/document/18/html/sql-commands.html)
- [PostgreSQLクライアントアプリケーション](https://www.postgresql.jp/document/18/html/reference-client.html)
- [PostgreSQLサーバアプリケーション](https://www.postgresql.jp/document/18/html/reference-server.html)

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
