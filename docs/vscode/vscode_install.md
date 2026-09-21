---
title: Install
parent: VSCode
layout: default
nav_enabled: true
nav_order: 1
---

# Install

## Windows

[Download Visual Studio Code](https://code.visualstudio.com/download?_exp_download=fb315fc982)からダウンロードする

---

## Ubuntu

1. 必要なツールをインストールする
   ```
   sudo apt update
   sudo apt install -y wget gpg
   ```
2. MicrosoftのGPGキーをダウンロードして保存する

   ```
   # キーをダウンロードして変換
   wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg

   # キーを適切なディレクトリに配置
   sudo install -D -o root -g root -m 644 microsoft.gpg /usr/share/keyrings/microsoft.gpg

   # 一時ファイルを削除
   rm -f microsoft.gpg
   ```

3. リポジトリを登録する
   ```
   echo "Types: deb
   URIs: https://packages.microsoft.com/repos/code
   Suites: stable
   Components: main
   Architectures: amd64,arm64,armhf
   Signed-By: /usr/share/keyrings/microsoft.gpg" | sudo tee /etc/apt/sources.list.d/vscode.sources
   ```
4. VSCodeをインストールする
   ```
   sudo apt update
   sudo apt install -y code
   ```
5. VSCodeのバージョンを確認する
   ```
   code --version
   ```

---
