---
title: Command
parent: Docker
layout: default
nav_enabled: true
nav_order: 3
---

# Command

## Docker 管理コマンド

| command          | description                                |
| ---------------- | ------------------------------------------ |
| `docker dockerd` | Dockerデーモンに関するコマンド             |
| `docker info`    | Dockerシステムの幅広い情報を表示する       |
| `docker inspect` | Dockerオブジェクト上のローレベル情報を返す |
| `docker version` | Docker バージョン情報を表示する            |

---

## イメージ用コマンド

| command          | description                                                     |
| ---------------- | --------------------------------------------------------------- |
| `docker build`   | Dockerfileからイメージを構築する                                |
| `docker commit`  | コンテナからイメージを作成する                                  |
| `docker export`  | コンテナのファイルシステムをtarアーカイブとして出力する         |
| `docker history` | イメージの履歴を表示する                                        |
| `docker images`  | イメージ一覧を表示する                                          |
| `docker import`  | tarアーカイブからコンテナのファイルシステムやイメージを作成する |
| `docker load`    | tarアーカイブ/標準入力からイメージを取り込む                    |
| `docker rmi`     | イメージを削除する                                              |
| `docker save`    | イメージをtarアーカイブに保存する                               |
| `docker tag`     | 対象イメージに元イメージを参照するタグを作成する                |

---

## コンテナ用コマンド

| command                    | description                                                            |
| -------------------------- | ---------------------------------------------------------------------- |
| `docker container attach`  | 標準入力、標準出力、標準エラー出力を実行中のコンテナに対して取り付ける |
| `docker container commit`  | コンテナからイメージを作成する                                         |
| `docker container cp`      | コンテナとローカルファイルシステム間でファイルやフォルダをコピーする   |
| `docker container create`  | 新しいコンテナを作成する                                               |
| `docker container diff`    | コンテナのファイルシステム上で、ファイルやディレクトリの変更を調査する |
| `docker container exec`    | 実行中のコンテナ内でコマンドを実行する                                 |
| `docker container export`  | コンテナのファイルシステムをtarアーカイブとして出力する                |
| `docker container inspect` | コンテナの詳しい情報を表示する                                         |
| `docker container kill`    | コンテナをキルする                                                     |
| `docker container logs`    | コンテナのログを取得する                                               |
| `docker container ls`      | コンテナ一覧を取得する                                                 |
| `docker container pause`   | コンテナを停止する                                                     |
| `docker container port`    | コンテナのポート割りあてを表示する                                     |
| `docker container prune`   | 停止したすべてのコンテナを削除する                                     |
| `docker container rename`  | コンテナ名を変更する                                                   |
| `docker container restart` | コンテナを再起動する                                                   |
| `docker container rm`      | コンテナを削除する                                                     |
| `docker container run`     | イメージからコンテナを作成して起動する                                 |
| `docker container start`   | コンテナを起動する                                                     |
| `docker container stats`   | コンテナのリソース利用統計情報を表示する                               |
| `docker container stop`    | コンテナを停止する                                                     |
| `docker container top`     | コンテナの実行中のプロセスを表示する                                   |
| `docker container unpause` | コンテナの一時停止を解除する                                           |
| `docker container update`  | コンテナの設定を更新する                                               |
| `docker container wait`    | コンテナを停止するまでブロックし、終了コードを表示する                 |
| `docker events`            | サーバからリアルタイムのイベントを取得                                 |

---

## Hub ・レジストリ用コマンド

| command         | description                                        |
| --------------- | -------------------------------------------------- |
| `docker login`  | Dockerレジストリにログインする                     |
| `docker logout` | Dockerレジストリからログアウトする                 |
| `docker pull`   | Dockerレジストリからイメージやリポジトリを取得する |
| `docker push`   | Dockerレジストリにイメージやリポジトリを送信する   |
| `docker search` | Docker Hubのイメージを検索する                     |

---

## ネットワークと接続用コマンド

| command                     | description                        |
| --------------------------- | ---------------------------------- |
| `docker network_connect`    | コンテナをネットワークに接続する   |
| `docker network_create`     | ネットワークを作成する             |
| `docker network_disconnect` | ネットワークからコンテナを切断する |
| `docker network_inspect`    | ネットワークの情報を表示する       |
| `docker network_ls`         | ネットワークを一覧表示する         |
| `docker network_rm`         | ネットワークを削除する             |

---

## 共有データ・ボリューム用コマンド

| command                 | description                    |
| ----------------------- | ------------------------------ |
| `docker volume_create`  | ボリュームを作成する           |
| `docker volume_inspect` | ボリュームの詳細情報を表示する |
| `docker volume_ls`      | ボリュームを一覧表示する       |
| `docker volume_rm`      | ボリュームを削除する           |

---

## 参考資料

- [Dockerコマンド](https://docs.docker.jp/engine/reference/commandline/index.html)
- [docker container (日本語版)](https://docs.docker.jp/engine/reference/commandline/container_toc.html)
- [docker container (英語版)](https://docs.docker.com/reference/cli/docker/container/)

---
