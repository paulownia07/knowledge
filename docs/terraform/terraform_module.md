---
title: module
parent: Terraform
layout: default
nav_enabled: true
nav_order: 2
---

# [module](https://developer.hashicorp.com/terraform/tutorials/modules/module)

## moduleとは

moduleとは同時に利用される複数のリソースをまとめたもの。  
まとめて定義することで再利用性が高まる。

---

## rootディレクトリの構成

```
root/
  main.tf
  providers.tf
  backend.tf
  terraform.tf
  terraform.tfvars
  variables.tf
  outputs.tf
  modules/
    module1/
    module2/
    module3/
```

---

## moduleディレクトリの構成

```
sample_module/
  main.tf
  variables.tf
  outputs.tf
```

### main.tf

```
resource "aws_instance" "example" {
  ami           = "ami-12345678"
  instance_type = var.instance_type

  tags = {
    Name = var.instance_name
  }
}
```

### variables.tf

```
variable "instance_name" {
  type        = string
  description = "EC2インスタンス名"
}

variable "instance_type" {
  type        = string
  default     = "t2.micro"
}
```

### outputs.tf

```
output "instance_id" {
  value = aws_instance.example.id
}

output "public_ip" {
  value = aws_instance.example.public_ip
}
```

---

## moduleの呼び出し

```
# rootディレクトリのmain.tf

module "sample_vpc" {
  source = "./modules/sample_module"

  instance_name = var.instance_name
  instance_type = var.instance_type
}
```

```
# rootディレクトリのvariables.tf (moduleディレクトリのvariables.tfの内容を包含する)

variable "instance_name" {
  type = string
}

variable "instance_type" {
  type        = string
  default     = "t2.micro"
}
```

```
# rootディレクトリのterraform.tfvars

instance_name = "dev-ec2"
instance_type = "t2.micro"
```

```
# rootディレクトリのoutputs.tf (moduleディレクトリのoutputs.tfの内容を包含する)

output "instance_id" {
  value = module.sample_vpc.instance_id
}

output "public_ip" {
  value = module.sample_vpc.public_ip
}
```

---
