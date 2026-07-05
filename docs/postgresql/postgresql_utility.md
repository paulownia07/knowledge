---
title: Utility Command
parent: PostgreSQL
layout: default
nav_enabled: true
nav_order: 10
---

# Utility Command

## SET

パラメータを設定変更するSQL

```
SET [LOCAL] parameter_name { TO | = } { value | DEFAULT};
```

---

## SHOW

パラメータの設定値を表示するSQL

```
SHOW { parameter_name | ALL};
```

---

## COPY

データをコピーするSQL

```
# テーブルのデータをファイルへコピーする
COPY Table_name TO 'abs_path' [[WITH] option];

# ファイルのデータをテーブルにコピーする
COPY Table_name FROM 'abs_path' [[WITH] option];

```

| option            | description                             |
| ----------------- | --------------------------------------- |
| `DELIMITER` dlmtr | 区切り文字を指定する (デフォルトはタブ) |
| `FORMAT csv`      | CSV形式で入出力する                     |
| `HEADER`          | ヘッダ行を指定                          |

---

## EXPLAIN

---

## VACUUM

不要領域を回収するSQL  
テーブルを指定しない場合、すべてテーブルを対象とする

```
VACUUM [FULL] [VERBOSE] [Table_name];
```

---

## ANALYZE

統計情報を更新するSQL  
テーブルを指定しない場合、すべてテーブルを対象とする

```
ANALYZE [Table_name];
```

---

## VACUUM ANALYZE

不要領域を回収と統計情報の更新をまとめて実行するSQL  
テーブルを指定しない場合、すべてテーブルを対象とする

```
VACUUM ANALYZE [Table_name];
```

---
