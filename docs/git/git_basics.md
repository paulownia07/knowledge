---
title: basics
parent: Git
layout: default
nav_enabled: true
nav_order: 3
---

# basics

## Git for Windowsのアップグレード

以下のコマンドをGit Bashから実行する

```
git update-git-for-windows
```

---

## 認証

GitHubやGitLabにアクセスして作業するには認証情報を保存する必要がある。Gitでは認証情報の保存方法として、Git Credential Managerを使用する方法がある。認証情報はOSの資格情報ストアに保存される。

1. Git Credential Managerをインストールする
2. Git Credential Managerがインストールされているか確認する
   ```
   git credential-manager --version
   ```
3. credential.helperの設定を行う
   ```
   git config --global credential.helper manager
   ```
4. `git pull`/`git clone`/`git clone`を実行し、ブラウザで認証を行う

---
