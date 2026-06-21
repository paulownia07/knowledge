---
title: GitHub Copilot
parent: GitHub
layout: default
nav_enabled: true
nav_order: 3
---

# [GitHub Copilot](https://docs.github.com/ja/copilot)

## チャット

チャットは2つの画面で使用可能である。

- チャット画面  
  VSCode画面上部の「Copilot」アイコンをクリックしてチャットを開く
- インラインチャット画面  
  VSCodeのエディター上で<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>i</kbd>を押下する

### インラインチャット画面での便利なショートカット

| shortcut                                                     | description                            |
| ------------------------------------------------------------ | -------------------------------------- |
| <kbd>Tab</kbd>                                               | コード補完の受け入れ                   |
| <kbd>Esc</kbd>                                               | コード補完の拒否                       |
| <kbd>Ctrl</kbd>+<kbd>→</kbd>                                 | 次の単語までのコード補完の受け入れ     |
| <kbd>Ctrl</kbd>+<kbd>]</kbd>                                 | コードの補完の次の候補を表示           |
| <kbd>Ctrl</kbd>+<kbd>[</kbd>                                 | コードの補完の前の候補を表示           |
| <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>i</kbd> | GitHub Copilotチャットへカーソルを移動 |

---

## プロンプト拡張機能

### チャット参加者

チャットを使用する際に、特定の仮想のチャット参加者に問いかけることでより正確な回答を得ることができる。

| participant  | description            |
| ------------ | ---------------------- |
| `@workspace` | 使用中のワークスペース |
| `@terminal`  | ターミナル             |
| `@vscode`    | VSCode                 |
| `@github`    | GitHub                 |
| `@azure`     | Azure                  |

### スラッシュコマンド

| command     | descriptioin                             |
| ----------- | ---------------------------------------- |
| `/new`      | 新しいファイルやプロジェクトを作成する   |
| `/explain`  | 説明を要求する                           |
| `/search`   | 検索したい内容を指定する                 |
| `/generate` | コードなどを自動生成する                 |
| `/fix`      | 問題点を修正する                         |
| `/optimize` | コードなどを最適化する                   |
| `/tests`    | テストケースやテストコードを自動生成する |
| `/doc`      | ドキュメントやコメントを自動生成する     |
| `/help`     | ヘルプを表示する                         |
| `/clear`    | 既存チャットの内容をクリアする           |

### チャット変数

---

## MCP サーバ

MCPサーバの設定ファイルは`.vscode/mcp.json`に登録する

```json
{
  "servers": {
    ...
  }
}
```

---
