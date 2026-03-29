# mvnpm MCP Server

An MCP server that connects to [mvnpm.org](https://mvnpm.org) — a Maven repository facade for NPM packages. It lets AI agents search, convert, and manage NPM packages as Maven/Gradle dependencies.

## Quick Start

Add the following to your Cline MCP settings:

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

No local dependencies, no API keys — just add and go.

## What it does

This MCP server gives your AI agent access to mvnpm tools so it can:

- **Search** NPM packages available as Maven artifacts
- **Convert** NPM package names to Maven/Gradle dependency snippets
- **Generate** POM files and ES module import maps
- **Browse** artifact contents (JAR/TGZ files)
- **Check** Maven Central sync status
- **Monitor** the sync pipeline and event logs

## Available Tools

| Tool | Description |
|------|-------------|
| `search_packages` | Find NPM packages available through mvnpm |
| `get_package_info` | Get full package metadata (licenses, dependencies, maintainers) |
| `list_versions` | List all available versions including dist-tags (latest, next, etc.) |
| `get_maven_coordinates` | Convert an NPM package name to Maven/Gradle dependency snippets |
| `get_pom` | Generate the Maven POM XML for a specific package version |
| `get_import_map` | Get an ES module import map JSON for a package |
| `browse_artifact_contents` | Explore files inside JAR or TGZ archives |
| `download_jar` | Download or create a JAR (this also triggers Maven Central sync) |
| `check_sync_status` | Check if a package version has been synced to Maven Central |
| `list_sync_pipeline` | View the sync pipeline stages and their status |
| `get_event_log` | Access sync events and error logs |

## Example prompts

- "Add the lit web component library to my pom.xml"
- "What's the Maven coordinate for @hotwired/stimulus?"
- "Is htmx synced to Maven Central?"
- "Generate an import map for lit and @vaadin/router"

## NPM to Maven name mapping

| NPM | Maven |
|-----|-------|
| `lit` | `org.mvnpm:lit` |
| `@hotwired/stimulus` | `org.mvnpm.at.hotwired:stimulus` |
| `@vaadin/router` | `org.mvnpm.at.vaadin:router` |

The groupId is always under `org.mvnpm`. Scoped packages use `org.mvnpm.at.<scope>`.

## More info

- [mvnpm.org](https://mvnpm.org)
- [AI Agent setup guide](https://mvnpm.org/ai-agent/)
- [GitHub](https://github.com/mvnpm/mvnpm)

## License

Apache-2.0
