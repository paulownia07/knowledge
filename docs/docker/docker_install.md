---
title: Install
parent: Docker
layout: default
nav_enabled: true
nav_order: 1
---

# Install

## Ubuntu

Docker EngineとDocker Composeをインストールする

1. コンフリクトを起こす可能性のあるパッケージをアンインストールする

   ```
   sudo apt remove $(dpkg --get-selections docker.io docker-compose docker-compose-v2 docker-doc podman-docker containerd runc | cut -f1)
   ```

2. apt パッケージのインデックスを更新する

   ```
   # Add Docker's official GPG key:
   sudo apt update
   sudo apt install ca-certificates curl
   sudo install -m 0755 -d /etc/apt/keyrings
   sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
   sudo chmod a+r /etc/apt/keyrings/docker.asc

   # Add the repository to Apt sources:
   sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
   Types: deb
   URIs: https://download.docker.com/linux/ubuntu
   Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
   Components: stable
   Architectures: $(dpkg --print-architecture)
   Signed-By: /etc/apt/keyrings/docker.asc
   EOF

   sudo apt update
   ```

3. 最新版のDockerをインストールする
   ```
   sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```
4. dockerのバージョンを確認する
   ```
   sudo docker version
   ```
5. ユーザをdockerグループに追加する
   ```
   sudo usermod -aG docker $USER
   ```
6. dockerデーモンを再起動する
   ```
   sudo service docker restart
   ```
7. docker デーモンの状況を確認する
   ```
   systemctl status docker
   ```

---

## 参考資料

- [Install Docker Engine on Ubuntu](https://docs.docker.jp/engine/getstarted/step_one.html)

---
