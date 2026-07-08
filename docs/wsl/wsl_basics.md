---
title: basics
parent: WSL
layout: default
nav_enabled: true
nav_order: 1
---

# basics

## Document

[Windows Subsystem for Linux のドキュメント](https://learn.microsoft.com/ja-jp/windows/wsl/)

---

## Install

管理者モードでPowerShellを開き、以下のコマンドを実行する

```
wsl --install
```

---

## Command

### 使用可能なディストリビューションの一覧を確認する

```
wsl --list --online
```

### ディストリビューションをインストールする

```
wsl --install -d <DistroName>
```

### インストールされているディストリビューションを確認する

```
wsl --list --verbose
```

### ディストリビューションを削除する

```
wsl --unregister <DistroName>
```

---
