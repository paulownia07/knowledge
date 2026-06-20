---
title: remote state
parent: Terraform
layout: default
nav_enabled: true
nav_order: 3
---

# [remote state](https://developer.hashicorp.com/terraform/language/state/remote-state-data)

## terraform_remote_stateとは

terraform_remote_stateとは、他のステートファイルで管理されているリソースのoutputs.tfに記載されている値を参照することができるDataブロックである

---

## data.tf

```
data "terraform_remote_state" "other_rerource" {
  backend = "s3"

  config = {
    bucket = "terraform-state-123456789012"
    key    = "other_rerource/terraform.tfstate"
    region = "ap-northeast-1"
  }
}
```

## terraform.tfvars

```
# 元のリソースのoutputs.tfでsample_valueという変数を定義しているとする

var1 = data.terraform_remote_state.other_rerource.outputs.sample_value
```

---
