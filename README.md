# Context7 MCP Server

A remote MCP server for up-to-date code documentation for LLMs and AI code editors. Context7 pulls version-specific documentation and code examples straight from the source and places them directly into your prompt.

## Setup

### Using tool CLI

Install the CLI from https://github.com/zerocore-ai/tool-cli

```bash
# Install from tool.store
tool install library/context7
```

```bash
# View available tools
tool info library/context7
```

```bash
# Resolve a library ID
tool call library/context7 -m resolve-library-id -p query="how to use hooks" -p libraryName=react
```

```bash
# Query library documentation
tool call library/context7 -m query-docs -p libraryId=/facebook/react -p query="how to use useEffect"
```

### Authentication

Context7 MCP uses OAuth 2.1 authentication. On first use, you'll be prompted to authorize access through your browser.

**Connection endpoint:**
- HTTP (OAuth): `https://mcp.context7.com/mcp/oauth`

## Tools

### `resolve-library-id`

Resolves a package/product name to a Context7-compatible library ID.

**Input:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `query` | string | Yes | The user's original question or task. This is used to rank results by relevance. |
| `libraryName` | string | Yes | Library name to search for and retrieve a Context7-compatible library ID. |

### `query-docs`

Retrieves and queries up-to-date documentation and code examples.

**Input:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `libraryId` | string | Yes | Exact Context7-compatible library ID (e.g., '/mongodb/docs', '/vercel/next.js'). |
| `query` | string | Yes | The question or task you need help with. Be specific and detailed. |

## License

Apache-2.0

## References

- https://context7.com
- https://github.com/upstash/context7
