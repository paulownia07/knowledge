---
title: Docker Compose
parent: Docker
layout: default
nav_enabled: true
nav_order: 5
---

# Docker Compose

## Docker Composeとは

Docker Composeとは、複数のコンテナを定義し実行する Docker アプリケーションのためのツール

---

## docker-compose.yml

[Compose file reference](https://docs.docker.com/reference/compose-file/)

---

## Docker Composeのコマンド

| command                | description                                               |
| ---------------------- | --------------------------------------------------------- |
| `docker-compose up`    | `docker-compose.yml`で定義されたコンテナを起動する        |
| `docker-compose build` | `Dockerfile`から生成されるイメージを再構築する            |
| `docker-compose ps`    | Composeが管理しているコンテナの状態に関する情報を表示する |
| `docker-compose run`   | 単発のコマンドを実行するためにコンテナを起動する          |
| `docker-compose logs`  | Composeが管理しているコンテナのログを表示する             |
| `docker-compose stop`  | コンテナを停止する                                        |
| `docker-compose rm`    | 停止しているコンテナを削除する                            |

---

## 参考資料

- [docker compose (日本語版)](https://docs.docker.jp/engine/reference/commandline/compose.html)
- [docker compose (英語版)](https://docs.docker.com/reference/cli/docker/compose/)

---
