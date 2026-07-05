---
title: GitHub Actions
parent: GitHub
layout: default
nav_enabled: true
nav_order: 2
---

# [GitHub Actions](https://docs.github.com/ja/actions)

## ワークフローファイル

ワークフローを定義するYAMLファイル  
`.github/workflows/`配下に任意の名前で配置する

```
my-project/
├─ .github/
│  ├─ workflows/
│     └─ example.yml
├─ src/
└─ docs/
```

| components                 | description          |
| -------------------------- | -------------------- |
| `name`                     | ワークフロー名       |
| `on`                       | ワークフロー実行起点 |
| `jobs`                     | ジョブの定義         |
| `jobs.<job_id>`            | ジョブ名 (ジョブID)  |
| `jobs.<job_id>.runs-on`    | ランナー             |
| `jobs.<job_id>.steps`      | ステップの定義       |
| `jobs.<job_id>.steps.run`  | シェルコマンドの実行 |
| `jobs.<job_id>.steps.uses` | アクションの呼び出し |

### on

[ワークフローをトリガーするイベント](https://docs.github.com/ja/actions/reference/workflows-and-actions/events-that-trigger-workflows)

```
# pushを起点とする場合
on: push

# pushとpull_requestを起点とする場合
on: [push, pull_request]
```

### runs-on

[runner images](https://github.com/actions/runner-images/tree/main)

| runner          | description |
| --------------- | ----------- |
| `ubuntu-latest` |             |
| `ubuntu-slim`   |             |
| `windows`       |             |
| `macos`         |             |

### uses

[Actions](https://github.com/marketplace?type=actions)

| action                    | description                                      |
| ------------------------- | ------------------------------------------------ |
| `actions/checkout@v6`     | リポジトリのソースコードをrunner環境に持ってくる |
| `actions/setup-python@v6` | Pythonのインストール                             |

```
steps:
- uses: actions/checkout@v6
- uses: actions/setup-python@v6
  with:
    python-version: '3.13'
- run: python my_script.py
```

---
