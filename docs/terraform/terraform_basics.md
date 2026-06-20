---
title: basics
parent: Terraform
layout: default
nav_enabled: true
nav_order: 1
---

# basics

## セットアップ

1. [Install Terraform](https://developer.hashicorp.com/terraform/install)からバイナリをダウンロードする
2. バージョンを確認する
   ```
   terraform -v
   ```
3. タブ補完機能を有効化する
   ```
   terraform -install-autocomplete
   ```
   > [!NOTE]
   > 「386」は32ビットの古いx86アーキテクチャ。
   > 「AMD64(x86-64)」はIntelとAMDが開発した互換性のある64ビットアーキテクチャ。
   > 「ARM64」はARMアーキテクチャの64ビット版。

---

## ファイル

| file             | description                                                     |
| ---------------- | --------------------------------------------------------------- |
| providers.tf     | providerの設定を記述するためのファイル                          |
| backend.tf       | stateファイルをクラウド上に保管する設定を行うためのファイル     |
| terraform.tf     | Terraform自体の設定や依存関係の設定を記述するするためのファイル |
| terraform.tfvars | 変数に具体的な値を設定するためのファイル                        |
| variables.tf     | 変数の定義を行うためのファイル                                  |
| outputs.tf       | 出力する変数の定義を行うためのファイル                          |
| main.tf          | 構築するリソース情報を定義するためのファイル                    |
| locals.tf        | 式や関数を使用した変数の設定を行うためのファイル                |

### providers.tf

```
# Configure the AWS Provider
provider "aws" {
    region = "ap-northeast-1"
    # AWS CLI設定ファイルを利用して権限を渡す
    shared_config_files = ["~/.aws/config"]
    shared_credentials_files = ["~/.aws/credentials"]
    profile = "PROFILE_NAME"
}
```

### backend.tf

```
terraform {
    #stateファイルを保管するS3バケットを指定する
    backend "s3" {
        bucket = "s3_bucket_name"
        key = "aaa/backend.tfstate"
        region = "ap-northeast-1"
        use_lock_file = true
    }
}
```

### terraform.tf

```
# Configure the AWS Provider
terraform {
    required_providers {
        aws = {
            source = "hashicorp/aws"
            version = "~> 5.0"
        }
    }
}
```

### terraform.tfvars

```
VARIABLE_NAME_1 = "hello"
VARIABLE_NAME_2 = 100
VARIABLE_NAME_3 = true
```

### variables.tf

```
variable "VARIABLE_NAME_1" {
    # 変数の型
    type = string|number|bool|list(<TYPE>)|set(<TYPE>)|map(<TYPE>)|tuple([<TYPE>, ...])|object({<ATTR NAME> = <TYPE>, ... })
    # 変数の説明
    description = "The description of the variable."
    # デフォルト値
    default =
    # 値のバリデーション
    validation =
    # センシティブな値かどうかのフラグ
    sensitive = true|false
    # nullを許容するかどうかのフラグ
    nullable = true|false
}
```

### outputs.tf

```
output "VALUE_NAME_1" {
    description = "The description of the value"
    value = RESOURCE_TYPE_NAME.LOCAL_RESOURCE_NAME.id
}
```

### main.tf

```
# resourceブロック : 個々のインフラオブジェクトの設定を記述するためのブロック
resource "RESOURCE_TYPE_NAME" "LOCAL_RESOURCE_NAME" {
    KEY1 = VALUE1
    KEY2 = VALUE2

    # terraform.tfvars で設定した変数の使用
    KEY3 = var.VARIABLE_NAME_3
    KEY4 = "${var.PREFIX}_VALUE4"

    # 記述したリソースの作成完了後にこのリソースを作成する
    depends_on = [RESOURCE_TYPE_NAME.LOCAL_RESOURCE_NAME]

    # リソースのライフサイクルを定義する
    lifecycle {
        # 新しいリソースを作成してから古いリソースを削除する
        create_before_destroy = true
        # リソースの破棄を防止する
        prevent_destroy = true
        # 指定した属性の変更を管理対象から除外する
        ignore_changes = []
        # 指定したリソースが変更されたとき、このリソースを再作成する
        replace_triggered_by = []
    }
}
```

### locals.tf

[Built-in Functions](https://developer.hashicorp.com/terraform/language/functions)

```
locals {
    KEY1 = max(var.num1, var.num2, var.num3)
    KEY2 = "${var.PREFIX}_VALUE2"
}
```

---

## 主要なコマンド

[Terraform CLI Documentation](https://developer.hashicorp.com/terraform/cli)

| command               | description                                              |
| --------------------- | -------------------------------------------------------- |
| `terraform init`      | 初期化処理の実行                                         |
| `terraform plan`      | 実行プランの表示                                         |
| `terraform apply`     | 環境を構築                                               |
| `terraform output`    | outputs.tf に記述した変数の値を出力する                  |
| `terraform destroy`   | 環境を削除                                               |
| `terraform validate`  | configが正しいか確認                                     |
| `terraform console`   | Terraformの文法を対話的に実行して試す                    |
| `terraform fmt`       | HCLを標準スタイルに整形する                              |
| `terraform import`    | 既存のリソースをTerraformリソースに紐づける              |
| `terraform login`     | HCP Terraformにログインする                              |
| `terraform refresh`   | リモートの状態と整合性をとるようにステートファイルを更新 |
| `terraform state`     | ステートファイルの操作                                   |
| `terraform test`      | Terraformモジュールのテストを実行                        |
| `terraform workspace` | ワークスペースを管理する                                 |
| `terraform -v`        | バージョンを確認する                                     |
| `terraform -help`     | コマンドを確認する                                       |

---

## Providers

| provider   | link                                                                                                        |
| ---------- | ----------------------------------------------------------------------------------------------------------- |
| AWS        | [AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)                           |
| Azure      | [Azure Provider](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)                     |
| GCP        | [Terraform provider for Google Cloud](https://registry.terraform.io/providers/hashicorp/google/latest/docs) |
| Kubernetes | [Kubernetes Provider](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs)             |
| Docker     | [Docker Provider](https://registry.terraform.io/providers/kreuzwerker/docker/latest/docs)                   |
| Snowflake  | [Snowflake Provider](https://registry.terraform.io/providers/snowflakedb/snowflake/latest/docs)             |
| Databricks | [Databricks Provider](https://registry.terraform.io/providers/databricks/databricks/latest/docs)            |
| Random     | [Random Provider](https://registry.terraform.io/providers/hashicorp/random/latest/docs)                     |

---

## リソースの作成

1. プロジェクトディレクトリを作成して移動する
2. 必要なファイルを作成し、編集する
3. 初期化を行う
   ```
   terraform init
   ```
4. 構築プランの確認を行う
   ```
   terraform plan
   ```
5. 環境の構築を行う
   ```
   terraform apply
   ```
6. 環境の削除を行う
   ```
   terraform destroy
   ```

---

## Expressions

[Expressions](https://developer.hashicorp.com/terraform/language/expressions)は値を取得、計算、変換するために使用する記述

---

## import

importブロックを利用して既存のリソースを取り込むことができる

1. コンソールからリソースを作成する
2. main.tfにimportするリソースの情報を記述する
   ```
   import {
    to = <RESOURCE_TYPE_NAME>.<LOCAL_RESOURCE_NAME>
    id = "<id>"
    }
   ```
3. 初期化を行う
   ```
   terraform init
   ```
4. 構築プランの確認を行う
   ```
   terraform plan --generate-config-out=import.tf
   ```
5. import
   ```
   terraform apply
   ```

---

## HCP Terraform

[What is HCP Terraform?](https://developer.hashicorp.com/terraform/cloud-docs)  
HCP(HashiCorp Cloud Platform) TerraformはHashiCorpが提供するマネージドサービス。

- ステートファイルの共有と管理
- Terraformコードのリモート実行
- Gitとの連携
- パスワードやクレデンシャルなどの管理
  が可能。

---
