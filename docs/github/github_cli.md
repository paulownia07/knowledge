---
title: GitHub CLI
parent: GitHub
layout: default
nav_enabled: true
nav_order: 4
---

# GitHub CLI
## Install
### Windows
#### install
```
winget install --id GitHub.cli --source winget
```

#### upgrade
```
winget upgrade --id GitHub.cli --source winget
```

---

### macOS
#### install
```
brew install gh
```

#### upgrade
```
brew upgrade gh
```

---

### Linux (Debian)
#### install
```
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

#### upgrade
```
sudo apt update
sudo apt install gh
```

---

### Linux (RPM)
#### install
```
sudo dnf install dnf5-plugins
sudo dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh
```

#### upgrade
```
sudo dnf update gh
```

---