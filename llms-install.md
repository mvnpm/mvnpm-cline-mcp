# mvnpm MCP Server — Installation Guide

## Server Details

- **Type**: Streamable HTTP (remote server, no local install needed)
- **URL**: `https://mvnpm.org/mcp`
- **Authentication**: None required
- **Dependencies**: None

## Cline MCP Configuration

Add to your Cline MCP settings:

```json
{
  "mcpServers": {
    "mvnpm": {
      "url": "https://mvnpm.org/mcp",
      "transportType": "streamableHttp"
    }
  }
}
```

## What this server does

Provides 11 tools for working with NPM packages as Maven/Gradle dependencies via mvnpm.org. Allows searching NPM packages, converting names to Maven coordinates, generating POM files and import maps, browsing artifact contents, and monitoring Maven Central sync status.

## NPM to Maven name mapping

- Non-scoped: `lit` becomes `org.mvnpm:lit`
- Scoped: `@hotwired/stimulus` becomes `org.mvnpm.at.hotwired:stimulus`
