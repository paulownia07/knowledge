---
title: basics
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 2
---

# basics

## PostgreSQL Documentation

[PostgreSQL Documentation](https://www.postgresql.org/docs/current/)

---

## コメント

```
-- 単一行コメント
/* 複数行コメント */
```

---

## ファイルからSQLの実行

### 実行手順

1. 拡張子は「.spl」のファイルを作成する
2. 以下のコマンドを実行する
   ```
   psql -U <user_name> -f <C:/file_name.sql>
   ```

### テンプレート

```
DROP DATABASE IF EXISTS result_2020;
CREATE DATABASE result_2020 WITH ENCODING = 'UTF-8';

\c result_2020 postgres;

DROP TABLE IF EXISTS product;
CREATE TABLE product (
    model char(5),
    name varchar(10),
    price integer,
    PRIMARY KEY (model)
);

BEGIN;
LOCK TABLE product;
INSERT INTO product VALUES
    ('PN001','aaa',1000),
    ('PN002','bbb',2000),
    ('PN003','ccc',30000),
    ('PN004','ddd',2000),
    ('PN005','eee',500);
COMMIT;

DROP TABLE IF EXISTS sales;
CREATE TABLE sales (
    id integer,
    day date,
    model char(5),
    quantity integer,
    PRIMARY KEY (id)
);

BEGIN;
LOCK TABLE sales;
INSERT INTO sales VALUES
    (1,'2020-01-07','PN005',7),
    (2,'2020-01-08','PN002',5),
    (3,'2020-01-12','PN004',3),
    (4,'2020-01-18','PN001',2),
    (5,'2020-01-22','PN005',10);
COMMIT;
```

---
