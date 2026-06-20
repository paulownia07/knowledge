---
title: AWS CLI
parent: AWS
layout: default
nav_enabled: true
nav_order: 2
---

# AWS CLI

## AWS CLIのインストール

[AWS CLI の最新バージョンのインストールまたは更新](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/getting-started-install.html)に従いAWS CLIをインストールする

---

## AWS CLIの設定

1. コマンドプロンプトで以下を実行

   ```
   aws configure
   ```

2. 「AWS Access Key ID」、「AWS Secret Access Key」、「Default region name」、「Default output format」を以下のように入力する
   ```
   AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
   AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
   Default region name [None]: ap-northeast-1
   Default output format [None]: json
   ```
3. `.aws/config`を以下のように編集する

   ```
   [default]
       region = ap-northeast-1
       output = json

   [profile developer]
       role_arn = arn:aws:iam::123456789012:role/role_name
       aws_mfa_device = arn:aws:iam::123456789012:mfa/mfa_device_name
       source_profile = default

   # teffaform用のprofile
   [profile terraformer]
       credential_process = aws configure export-credentials --profile developer
   ```

---

## AWS CLIでのコマンドの実行

1. [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/)でコマンドを調査する
2. `params.json`を作成する
3. 入力パラメータのテンプレートを取得して、`params.json`にペーストする
   ```
   aws <command> <subcommand> --generate-cli-skeleton
   ```
4. `params.json`を編集する
5. 環境変数`AWS_PROFILE`に使用するプロファイル名を設定する
   ```
   #Windows
   set AWS_PROFILE=developer
   ```
   ```
   #Linux
   export AWS_PROFILE=developer
   ```
6. ファイルからのパラメータ入力してコマンドを実行する
   ```
   aws <command> <subcommand> --cli-input-json file://params.json
   ```

---
