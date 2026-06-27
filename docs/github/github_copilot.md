---
title: GitHub Copilot
parent: GitHub
layout: default
nav_enabled: true
nav_order: 3
---

# [GitHub Copilot](https://docs.github.com/ja/copilot)

## 一般的なプロジェクトのファイル構成

```
my-project/
├─ .github/
│  ├─ copilot-instructions.md
│  ├─ instructions/
│  │  ├─ python.instructions.md
│  │  └─ docs.instructions.md
│  └─ prompts/
│     ├─ review.prompt.md
│     └─ design.prompt.md
├─ AGENTS.md
├─ src/
└─ docs/
```

---

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

## チャットモード

| mode  | description                                        |
| ----- | -------------------------------------------------- |
| Ask   | 質問や相談を行うためのモード                       |
| Plan  | コード変更を行わずに実装計画を作成するためのモード |
| Agent | 実装作業を実行するためのモード                     |

---

## プロンプト拡張機能

### [チャット参加者](https://code.visualstudio.com/docs/agents/reference/ai-features-cheat-sheet#_chat-participants)

チャットを使用する際に、特定の仮想のチャット参加者に問いかけることでより正確な回答を得ることができる。

| participant  | description            |
| ------------ | ---------------------- |
| `@workspace` | 使用中のワークスペース |
| `@terminal`  | ターミナル             |
| `@vscode`    | VSCode                 |
| `@github`    | GitHub                 |
| `@azure`     | Azure                  |

### [スラッシュコマンド](https://code.visualstudio.com/docs/agents/reference/ai-features-cheat-sheet#_slash-commands)

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

### [チャット変数](https://code.visualstudio.com/docs/agents/reference/ai-features-cheat-sheet#_chat-tools)

特定のリソース情報やツールをプロンプトに含めるための機能

| variable                                     | description                                      |
| -------------------------------------------- | ------------------------------------------------ |
| `#changes`                                   | ソース管理の変更一覧を追加する                   |
| `#{FILE_NAME \| FOLDER_NAME \| SYMBOL_NAME}` | ファイル、フォルダ、シンボルを追加する           |
| `#problems`                                  | problemにある問題情報を追加する                  |
| `#selection`                                 | 現在の選択範囲を追加する                         |
| `#terminalSelction`                          | ターミナルの選択範囲を追加する                   |
| `#terminalLastCommand`                       | ターミナルで実行した最後のコマンドを追加する     |
| `#codebase {KEYWORD}`                        | コードベースをキーワードで検索して結果を追加する |
| `#fetch {URL}`                               | 指定したURLのコンテンツを取得して追加する        |
| `#githubRepo {REPOSITORY}`                   | GitHubリポジトリ内の情報を追加する               |
| `#runCommands {COMMAND}`                     | 指定したコマンドを実行する                       |

### プロンプトファイル

独自にプロンプトファイルを作成することができる  
ファイルの拡張子は`.prompt.md`であり、`.github/prompts/`に配置する  
ファイル名が`sample_prompt.prompt.md`の場合、`/sample_prompt`で呼び出す

```
---
mode: '???' <!-- ask, plan, agentの3つから選択 -->
model: ??? <!-- モデルを指定する -->
tools: ['???', '???', '???'] <!-- 使用するツールをリスト形式で記述する -->
description: '???' <!-- このファイルの説明を記述する -->
---

????????????????????
????????????????????
????????????????????
```

### カスタムインストラクション

???  
ファイルの拡張子は`.instructions.md`であり、`.github/instructions/`に配置する  
ファイル名が`sample_instruction.instructions.md`の場合、`/sample_instruction`で呼び出す

```
---
applyTo: '???' <!-- 命令を適用するファイルパターンを指定する -->
description: '???' <!-- このファイルの説明を記述する -->
---

????????????????????
????????????????????
????????????????????
```

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

### ツールセット

複数のツールを管理するためのファイル  
拡張子は`.jsonc`

```jsonc
{
  "toolset_name": {
    "tools": ["tool_name", "tool_name", "tool_name"],
    "description": "?????",
    "icon": "???",
  },
}
```

---
