---
title: Boto3
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# Boto3

[Boto3](https://docs.aws.amazon.com/boto3/latest/)はPythonからAWSの各種サービスを操作・自動化するための公式SDK

---

## モジュールの読み込み

```Python
import boto3
```

---

## S3

### バケット一覧を取得

```Python
import boto3

s3 = boto3.client("s3")
response = s3.list_buckets()
bucket_list = [bucket["Name"] for bucket in response["Buckets"]]
```

### バケット内のオブジェクトの一覧を取得

```Python
import boto3

s3 = boto3.resource('s3')
bucket = s3.Bucket(bucket_name)
object_list = [object.key for object in bucket.objects.all()]
```

### 特定のフォルダ内のファイル一覧取得

```Python
import boto3

s3_client = boto3.client("s3")
response = s3_client.list_objects_v2(Bucket=bucket_name, Prefix="path/to/source/")
files = [obj["Key"] for obj in response.get("Contents", [])]
```

### CSVファイルを読み込む

```Python
import io
import pandas
import boto3

s3_client = boto3.client("s3")
response = s3_client.get_object(Bucket=bucket_name, Key="path/to/source/file.csv")
csv_content = response["Body"].read().decode("utf-8")
df = pd.read_csv(io.StringIO(csv_content))
```

### テキストファイルを読み込む

```Python
import boto3

s3_client = boto3.client("s3")
response = s3_client.get_object(Bucket=bucket_name, Key="path/to/source/file.txt")
#ファイル全体を読み込む
contents = response["Body"].read().decode("utf-8")
#ファイルの内容を一行ずつ読み込みリスト化
rows = contents.splitlines()
```

#XMLファイルを読み込む

```Python
import xml.etree.ElementTree as ET
import boto3

s3_client = boto3.client("s3")
response = s3_client.get_object(Bucket=bucket_name, Key="path/to/source/file.xml")
xml_content = response["Body"].read().decode("utf-8")
root = ET.fromstring(xml_content)
```

#JSONファイルを読み込む

```Python
import json
import boto3

s3_client = boto3.client("s3")
response = s3_client.get_object(Bucket=bucket_name, Key="path/to/source/file.xml")
json_content = response["Body"].read().decode("utf-8")
parsed_data = json.loads(json_content)
```

#ファイルを作成して上書き保存する

```Python
import boto3

s3_client = boto3.client("s3")
response = s3_client.put_object(Body=contents, Bucket=bucket_name, Key="path/to/source/file.txt")
```

#ファイルをアップロードする

```Python
import boto3

s3_client = boto3.client("s3")
s3.upload_file("local/path/file.txt", bucket_name, "s3/path/file.txt")
```

#ファイルをダウンロードする

```Python
import boto3

s3_client = boto3.client("s3")
s3_client.download_file(bucket_name, "s3/path/file.txt", "local/path/file.txt")
```

---
