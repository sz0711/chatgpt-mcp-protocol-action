# 🤖 chatgpt-mcp-protocol-action

> Connect your custom ChatGPT to the Microsoft Learn documentation ecosystem via the Model Context Protocol (MCP).

[![License](https://img.shields.io/badge/license-MIT-green.svg)](#license)
[![Status](https://img.shields.io/badge/status-stable-blue)](https://github.com/sz0711/chatgpt-mcp-protocol-action)

---

## Overview

A minimal OpenAI-compatible action schema that wires a **custom ChatGPT** to the [Microsoft Learn MCP Server](https://github.com/microsoftdocs/mcp) via **JSON-RPC 2.0**, giving your GPT live access to Microsoft's technical documentation, code samples, and learning content.

### Key Capabilities

- **Zero-code setup** — drop a single JSON schema into your GPT's Actions tab and you're done
- **Microsoft Learn integration** — real-time access to official docs, SDK references, and learning paths
- **OpenAI-compatible schema** — standard OpenAPI 3.1 action format accepted natively by ChatGPT
- **No authentication required** — public MCP endpoint, no keys or secrets needed
- **Works everywhere** — ChatGPT web interface and mobile app

---

## How It Works

```
Custom GPT (Actions tab)
    └── action.json  (OpenAPI 3.1 schema)
            └── POST https://learn.microsoft.com/api/mcp/openai-compatible
                    └── JSON-RPC 2.0 request
                            └── MCP Server response (docs, tools, content)
```

### Supported MCP Methods

| Method | Description |
|--------|-------------|
| `initialize` | Handshake — negotiates protocol version and capabilities |
| `tools/list` | Returns the list of available MCP tools |
| `tools/call` | Executes a tool and returns documentation content |

---

## Getting Started

### Prerequisites

- A [ChatGPT Plus](https://chat.openai.com) subscription (required to create and use custom GPTs)
- A browser — no local tooling, SDKs, or accounts required beyond ChatGPT

### Setup

1. Go to [chat.openai.com](https://chat.openai.com)
2. Navigate to **Explore GPTs** → **My GPTs** → **Create a GPT**
3. In the creation flow, go to the **Actions** tab
4. Click **Create new action**
5. For **Authentication**, select **None**
6. For the **Schema**, paste the raw URL to the `action.json` file:
   `https://raw.githubusercontent.com/sz0711/chatgpt-mcp-protocol-action/main/action.json`

### Schema Options

| Field | Value |
|-------|-------|
| Authentication | None |
| Schema source | Raw URL of `action.json` from this repository |
| Privacy Policy URL | *(optional)* |

---

## Technology Stack

| Component | Detail |
|-----------|--------|
| OpenAPI | 3.1.0 |
| Protocol | JSON-RPC 2.0 |
| MCP Server | [Microsoft Learn MCP](https://github.com/microsoftdocs/mcp) |
| Endpoint | `https://learn.microsoft.com/api/mcp/openai-compatible` |

---

## License

This project is licensed under the [MIT License](LICENSE).

This project uses the [Microsoft Model Context Protocol (MCP)](https://github.com/microsoftdocs/mcp),
© Microsoft, licensed under the [MIT License](https://github.com/microsoftdocs/mcp/blob/main/LICENSE).

## Disclaimer

Private project. Provided without warranty. Use at your own risk.

---

> Built to bring Microsoft's knowledge graph directly into your ChatGPT conversations.
