---
title: MCP
parent: AI
layout: default
nav_enabled: true
nav_order: 4
---

# MCP

## MCPサーバ

| MCP server                                                                                   | description                                                     |
| -------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| [AWS MCP Server](https://docs.aws.amazon.com/agent-toolkit/latest/userguide/mcp-server.html) | AWSのMCPサーバ                                                  |
| [Terraform MCP Server](https://github.com/hashicorp/terraform-mcp-server)                    | TerraformのMCPサーバ                                            |
| [Azure MCP Server](https://learn.microsoft.com/ja-jp/azure/developer/azure-mcp-server/)      | AzureのMCPサーバ                                                |
| [Google Cloud MCP Servers](https://docs.cloud.google.com/mcp)                                | Google CloudのMCPサーバ                                         |
| [GitHub MCP Server](https://github.com/github/github-mcp-server)                             | GitHubを操作可能にするMCPサーバ                                 |
| [Microsoft Learn MCP Server](https://learn.microsoft.com/ja-jp/training/support/mcp)         | Microsoftの公式ドキュメントから直接取得可能にするMCPサーバ      |
| [FileSystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)       | FileSystemを操作可能にするMCPサーバ                             |
| [Desktop Commander](https://github.com/wonderwhy-er/DesktopCommanderMCP)                     | Claude Desktopをターミナルやファインダーのように扱えるMCPサーバ |
| [Context7](https://github.com/upstash/context7)                                              | 最新ライブラリの知識をLLMに提供するためのMCPサーバ              |
| [Fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch)                 | WebページをMarkdown形式に変換できるMCPサーバ                    |
| [draw.io MCP server](https://www.drawio.com/docs/manual/generate/drawio-mcp-server/)         | draw.ioのMCPサーバ                                              |

---

### MCPサーバ構成ファイル

```json
{
  "inputs": [
    {
      "type": "promptString",
      "id": "xxxxx",
      "description": "?????",
      "password": true
    }
  ],
  "servers": {
    "<mcp_name>": {
      "type": "http",
      "url": "https://???????/mcp/"
    }
  }
}
```

#### servers (http/sseサーバの場合)

MCPサーバの設定を定義する

| component                     | description                                                                | type                     |
| ----------------------------- | -------------------------------------------------------------------------- | ------------------------ |
| `.servers.<mcp_name>.type`    | サーバタイプを指定する (`"http"\|"sse"\|"stdio"`)                          | `"http"\|"sse"\|"stdio"` |
| `.servers.<mcp_name>.url`     | MCPサーバエンドポイントのURLを指定する                                     | `"http"\|"sse"`          |
| `.servers.<mcp_name>.headers` | MCPサーバへのリクエストヘッダを指定する                                    | `"http"\|"sse"`          |
| `.servers.<mcp_name>.command` | MCPサーバを起動するコマンドを指定する (`"npx"\|"uvx"\|"python"\|"docker"`) | `"stdio"`                |
| `.servers.<mcp_name>.args`    | MCPサーバを起動するためのコマンドの引数をリスト形式で指定する              | `"stdio"`                |
| `.servers.<mcp_name>.env`     | MCPサーバを起動するためのコマンドで使用する環境変数を指定する              | `"stdio"`                |

#### inputs

MCPサーバ起動時に必要な入力値を指定する

| component            | description                                     | type                           |
| -------------------- | ----------------------------------------------- | ------------------------------ |
| `inputs.type`        | 入力値のタイプ (`"promptString"\|"pickString"`) | `"promptString"\|"pickString"` |
| `inputs.id`          | 入力値を一意に特定するID                        | `"promptString"\|"pickString"` |
| `inputs.description` | 入力値の説明                                    | `"promptString"\|"pickString"` |
| `inputs.default`     | 入力値のデフォルト                              | `"promptString"\|"pickString"` |
| `inputs.password`    | 入力値が機微情報であるか (`true\|false`)        | `"promptString"`               |
| `inputs.options`     | 選択肢のリスト                                  | `"pickString"`                 |

---
