# Tilnote MCP Server

An [MCP (Model Context Protocol)](https://modelcontextprotocol.io) server that lets AI assistants create, read, search, and update notes on [Tilnote](https://tilnote.io). Works with Claude Code, Claude Desktop, Google Antigravity, and OpenAI Codex CLI.

## Tools

| Tool | Description |
|------|-------------|
| `create_note` | Create a new markdown note (saved as draft) |
| `get_note` | Get the full content of a note by page ID |
| `list_notes` | List your recent notes with excerpts |
| `search_notes` | Search notes by keyword |
| `update_note` | Update the title or content of an existing note |

## Prerequisites

- **Node.js 18+** — [https://nodejs.org](https://nodejs.org) (includes `npx`)

## Setup

### 1. Get your API key

Go to [https://tilnote.io/tilnote-api](https://tilnote.io/tilnote-api) to generate your API key.

### 2. Configure your MCP client

#### Claude Code (`.mcp.json`)

```json
{
  "mcpServers": {
    "tilnote": {
      "command": "npx",
      "args": ["-y", "tilnote-mcp-server"],
      "env": {
        "TILNOTE_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

#### Claude Desktop (`claude_desktop_config.json`)

```json
{
  "mcpServers": {
    "tilnote": {
      "command": "npx",
      "args": ["-y", "tilnote-mcp-server"],
      "env": {
        "TILNOTE_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

#### Google Antigravity

Open: Manage MCP Servers → View raw config → `~/.gemini/antigravity/mcp_config.json`

```json
{
  "mcpServers": {
    "tilnote": {
      "command": "npx",
      "args": ["-y", "tilnote-mcp-server"],
      "env": {
        "TILNOTE_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

Restart Antigravity after saving.

#### OpenAI Codex CLI

Add to `~/.codex/config.toml`:

```toml
[mcp_servers.tilnote]
command = "npx"
args = ["-y", "tilnote-mcp-server"]
env = { TILNOTE_API_KEY = "your_api_key_here" }
```

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `TILNOTE_API_KEY` | Yes | Your Tilnote API key |

## License

MIT

---

# Tilnote MCP 서버

[Tilnote](https://tilnote.io)에 노트를 생성, 조회, 검색, 수정할 수 있는 [MCP (Model Context Protocol)](https://modelcontextprotocol.io) 서버입니다. Claude Code, Claude Desktop, Google Antigravity, OpenAI Codex CLI와 연동하여 사용합니다.

## 도구

| 도구 | 설명 |
|------|------|
| `create_note` | 마크다운 노트 생성 (초안으로 저장) |
| `get_note` | 페이지 ID로 노트 전체 내용 조회 |
| `list_notes` | 최근 노트 목록과 요약 조회 |
| `search_notes` | 키워드로 노트 검색 |
| `update_note` | 기존 노트의 제목 또는 내용 수정 |

## 사전 요구 사항

- **Node.js 18+** — [https://nodejs.org](https://nodejs.org) 에서 설치 (`npx` 포함)

## 설정

### 1. API 키 발급

[https://tilnote.io/tilnote-api](https://tilnote.io/tilnote-api) 에서 API 키를 발급받으세요.

### 2. MCP 클라이언트 설정

#### Claude Code (`.mcp.json`)

```json
{
  "mcpServers": {
    "tilnote": {
      "command": "npx",
      "args": ["-y", "tilnote-mcp-server"],
      "env": {
        "TILNOTE_API_KEY": "발급받은_API_키"
      }
    }
  }
}
```

#### Claude Desktop (`claude_desktop_config.json`)

```json
{
  "mcpServers": {
    "tilnote": {
      "command": "npx",
      "args": ["-y", "tilnote-mcp-server"],
      "env": {
        "TILNOTE_API_KEY": "발급받은_API_키"
      }
    }
  }
}
```

#### Google Antigravity

Manage MCP Servers → View raw config → `~/.gemini/antigravity/mcp_config.json` 열기

```json
{
  "mcpServers": {
    "tilnote": {
      "command": "npx",
      "args": ["-y", "tilnote-mcp-server"],
      "env": {
        "TILNOTE_API_KEY": "발급받은_API_키"
      }
    }
  }
}
```

저장 후 Antigravity를 재시작하세요.

#### OpenAI Codex CLI

`~/.codex/config.toml` 에 추가:

```toml
[mcp_servers.tilnote]
command = "npx"
args = ["-y", "tilnote-mcp-server"]
env = { TILNOTE_API_KEY = "발급받은_API_키" }
```

## 환경 변수

| 변수 | 필수 | 설명 |
|------|------|------|
| `TILNOTE_API_KEY` | 필수 | 틸노트 API 키 |

## 라이선스

MIT
