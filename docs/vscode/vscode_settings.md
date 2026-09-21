---
title: settings
parent: VSCode
layout: default
nav_enabled: true
nav_order: 3
---

# settings

## settings.json

```
{
  // フォントサイズの設定（単位 px）
  "editor.fontSize": 16,
  // 保存時に自動でフォーマットを実行する
  "editor.formatOnSave": true,
  // ファイル保存時に不要な空白を削除する
  "files.trimTrailingWhitespace": true,
  // 画面の端でテキストを折り返す
  "editor.wordWrap": "on",
  // デフォルトの文字コードをUTF-8に指定
  "files.encoding": "utf8",
  // 空白文字を見えるようにする
  "editor.renderWhitespace": "all",
  // 改行コードをLFで固定する
  "files.eol": "\n"
  // スペースやタブを可視化する
  editor.renderWhitespace: "all",
  // 入力中に自動で補完候補を表示するかどうか (IntelliSenseを使用するかどうか)
  "editor.quickSuggestions": false,
  // GitHub Copilotを有効化するかどうか
  "github.copilot.enable": {
    "*": false
  },
  // GitHub Copilotのインライン補完を有効化するかどうか
  "editor.inlineSuggest.enabled": false,

  // Python拡張機能設定
  // pytestをテストフレームワークとして使用するかどうか
  "python.testing.pytestEnabled": true,
  // unittestをテストフレームワークとして使用するかどうか (pytestを使用する場合はfalseとする)
  "python.testing.unittestEnabled": false,
  // テストディレクトリを指定する
  "python.testing.pytestArgs": ["tests"]

  // Pylanceの設定
  "python.analysis.typeCheckingMode": "strict",

  // Pythonファイル専用設定
  "[python]": {
    // フォーマッタとしてruffを使用する
    "editor.defaultFormatter": "charliermarsh.ruff",
    //タブサイズを指定する
    "editor.tabSize": 4,
  },

  "[markdown]": {
    // フォーマッタとしてprettierを指定する
    "editor.defaultFormatter": "esbenp.prettier-vscode",
  },

  "[json]":{
    // タブサイズを指定する
    "editor.tabSize": 2,
  },

  "[jsonc]": {
    // タブサイズを指定する
    "editor.tabSize": 2
  },

  "[yaml]": {
    // タブサイズを指定する
    "editor.tabSize": 2
  }
}
```

---
