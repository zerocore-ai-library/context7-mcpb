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
tool call library/context7 -m resolve-library-id -p libraryName=react
```

```bash
# Get library documentation
tool call library/context7 -m get-library-docs -p context7CompatibleLibraryID=/facebook/react
```

### Authentication

Context7 MCP uses OAuth 2.1 authentication. On first use, you'll be prompted to authorize access through your browser.

**Connection endpoint:**
- HTTP (OAuth): `https://mcp.context7.com/mcp/oauth`

## Tools

### `resolve-library-id`

Resolve a general library name into a Context7-compatible library ID.

**Input:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `libraryName` | string | Yes | The name of the library to search for (e.g., "react", "nextjs", "mongodb") |

### `get-library-docs`

Retrieve documentation for a library using a Context7-compatible library ID.

**Input:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `context7CompatibleLibraryID` | string | Yes | Exact Context7-compatible library ID (e.g., /mongodb/docs, /vercel/next.js) |
| `topic` | string | No | The topic or question to focus the documentation on |
| `tokens` | number | No | Maximum number of tokens to return (default: 10000) |

## License

Apache-2.0

## References

- https://context7.com
- https://github.com/upstash/context7
