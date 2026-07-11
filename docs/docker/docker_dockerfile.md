---
title: Dockerfile
parent: Docker
layout: default
nav_enabled: true
nav_order: 4
---

# Dockerfile

## Dockerfileの命令

| Instruction   | Description                                                                                                |
| ------------- | ---------------------------------------------------------------------------------------------------------- |
| `ADD`         | ビルドコンテクストやリモートのURLからイメージへファイルをコピーする                                        |
| `ARG`         | docker buildする際に指定できる引数を宣言する                                                               |
| `CMD`         | コンテナ起動後に指定された命令を実行する (コマンドや引数を変更して実行できる)                              |
| `COPY`        | ファイルやディレクトリをコピーする                                                                         |
| `ENTRYPOINT`  | コンテナの起動時に実行する実行可能ファイルとデフォルト引数を指定する(コマンドや引数を変更して実行できない) |
| `ENV`         | 環境変数を設定する (環境変数の型は文字列)                                                                  |
| `EXPOSE`      | プロセスの接続ポートを指定する (注意: 使用するポートを宣言するだけ)                                        |
| `FROM`        | ベースイメージを指定する                                                                                   |
| `HEALTHCHECK` | ヘルスチェックの方法をカスタマイズする                                                                     |
| `LABEL`       | イメージにラベルを付与する                                                                                 |
| `MAINTAINER`  | イメージのAuthorメタデータに指定された文字列を設定する                                                     |
| `ONBUILD`     | 他のイメージのベースイメージとして呼び出されたときに実行される命令を指定する                               |
| `RUN`         | ビルドコマンドを実行する                                                                                   |
| `SHELL`       | ビルド時のシェルを指定する                                                                                 |
| `STOPSIGNAL`  | docker stopする際に、コンテナで実行しているプログラムに対して送信するシグナルを変更する                    |
| `USER`        | ユーザやグループIDを設定する                                                                               |
| `VOLUME`      | ボリュームマウントを作成する                                                                               |
| `WORKDIR`     | ワーキングディレクトリを変更する                                                                           |

---

## FROM

### サンプルイメージ

| image         | description                                        | link                                 |
| ------------- | -------------------------------------------------- | ------------------------------------ |
| `hello-world` | Hello World! (an example of minimal Dockerization) | https://hub.docker.com/_/hello-world |

### Linuxのイメージ

| image         | description  | link                                 |
| ------------- | ------------ | ------------------------------------ |
| `ubuntu`      | Ubuntu       | https://hub.docker.com/_/ubuntu      |
| `centos`      | CentOS       | https://hub.docker.com/_/centos      |
| `debian`      | DebianOS     | https://hub.docker.com/_/debian      |
| `fedora`      | Fedora       | https://hub.docker.com/_/fedora      |
| `busybox`     | BizyBox      | https://hub.docker.com/_/busybox     |
| `alpine`      | Alpine Linux | https://hub.docker.com/_/alpine      |
| `amazonlinux` | Amazon Linux | https://hub.docker.com/_/amazonlinux |
| `oraclelinux` | Oracle Linux | https://hub.docker.com/_/oraclelinux |

### プログラミング言語のイメージ

| image            | description       | link                                    |
| ---------------- | ----------------- | --------------------------------------- |
| `openjdk`        | Javaの実行環境    | https://hub.docker.com/_/openjdk        |
| `python`         | Pythonの実行環境  | https://hub.docker.com/_/python         |
| `php`            | PHPの実行環境     | https://hub.docker.com/_/php            |
| `ruby`           | Rubyの実行環境    | https://hub.docker.com/_/ruby           |
| `perl`           | Perlの実行環境    | https://hub.docker.com/_/perl           |
| `gcc`            | C/C++コンパイラ   | https://hub.docker.com/_/gcc            |
| `node`           | Node.js           | https://hub.docker.com/_/node           |
| `rust`           | Rust              | https://hub.docker.com/_/rust           |
| `amazoncorretto` | Corretto(OpenJDK) | https://hub.docker.com/_/amazoncorretto |

### サービスのイメージ

| image           | description                           | link                                   |
| --------------- | ------------------------------------- | -------------------------------------- |
| `httpd`         | Apache HTTP Server                    | https://hub.docker.com/_/httpd         |
| `nginx`         | Nginx                                 | https://hub.docker.com/_/nginx         |
| `tomcat`        | Apache Tomcat                         | https://hub.docker.com/_/tomcat        |
| `mysql`         | MySQL                                 | https://hub.docker.com/_/mysql         |
| `postgres`      | PostgreSQL                            | https://hub.docker.com/_/postgres      |
| `mariadb`       | MariaDB                               | https://hub.docker.com/_/mariadb       |
| `mongo`         | MongoDB                               | https://hub.docker.com/_/mongo         |
| `redis`         | Redis                                 | https://hub.docker.com/_/redis         |
| `cassandra`     | Apache Cassandra                      | https://hub.docker.com/_/cassandra     |
| `wordpress`     | WordPress (MySQLまたはMariaDBが必要)  | https://hub.docker.com/_/wordpress     |
| `nextcloud`     | NextCloud                             | https://hub.docker.com/_/nextcloud     |
| `redmine`       | Redmine (PostgreSQLまたはMySQLが必要) | https://hub.docker.com/_/redmine       |
| `elasticsearch` | Elasticsearch                         | https://hub.docker.com/_/elasticsearch |
| `kibana`        | Kibana                                | https://hub.docker.com/_/kibana        |
| `logstash`      | Logstash                              | https://hub.docker.com/_/logstash      |
| `fluentd`       | Fluentd                               | https://hub.docker.com/_/fluentd       |
| `spark`         | Apache Spark                          | https://hub.docker.com/_/spark         |
| `flink`         | Apache Flink                          | https://hub.docker.com/_/flink         |
| `maven`         | Apache Maven                          | https://hub.docker.com/_/maven         |
| `gradle`        | Gradle                                | https://hub.docker.com/_/gradle        |
| `registry`      | Dockerレジストリ                      | https://hub.docker.com/_/registry      |

---

## RUN

### Ubuntu

```
RUN apt-get update && \
    apt-get install -y curl vim git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
```

### CentOS

```
RUN dnf -y update && \
    dnf -y install curl vim git && \
    dnf clean all
```

### Amazon Linux

```
RUN dnf -y install curl vim git && \
    dnf clean all
```

### Python

```
RUN pip install --no-cache-dir -r requirements.txt
```

---

## WORKDIR

```
WORKDIR /app
```

---

## ENV

```
ENV APP_ENV=production
ENV PORT=8080
```

---

## COPY

```
COPY requirements.txt /app/
COPY src/ /app/src/
```

---

## USER

```
RUN useradd -m docker_user
USER docker_user
```

---

## ENTRYPOINT

```
ENTRYPOINT ["python", "main.py"]

```

---

## CMD

```
CMD ["python", "main.py"]
```

---

## ENTRYPOINT & CMD

```
# コマンド固定、引数可変の場合 (CMDにデフォルト引数を設定する)
ENTRYPOINT ["python", "main.py"]
CMD ["--arg1", "aaa", "--arg2", "100"]
```

---

## 参考資料

- [Dockerfile リファレンス](https://docs.docker.jp/engine/reference/builder.html)
- [Dockerfile reference](https://docs.docker.com/reference/dockerfile/)

---
