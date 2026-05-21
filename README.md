# SigNoz MCP Plugin

Connects Cursor to the [SigNoz MCP server](https://github.com/SigNoz/signoz-mcp-server) so you can query metrics, traces, logs, alerts, and dashboards using natural language.

## What you need

- A [SigNoz Cloud](https://signoz.io/) account
- [Cursor](https://cursor.com/) IDE

## Getting started

1. Open Cursor Settings and go to the **Plugins** section.
2. Install the **signoz-mcp** plugin.
3. When prompted, select your region from the **SigNoz Region** dropdown (`us`, `eu`, or `in`). Not sure which region? Go to **Settings > Ingestion** in SigNoz — the region is in your endpoint URL (e.g. `ingest.us.signoz.cloud` → `us`).
4. Authenticate the SigNoz MCP server when prompted. Enter your SigNoz instance URL and API key.

Create an API key under **Settings > API Keys** in SigNoz. Only Admin users can create API keys.

## Self-hosted SigNoz

If you run SigNoz yourself, use this config in `.cursor/mcp.json` instead:

```json
{
  "mcpServers": {
    "signoz": {
      "command": "/path/to/signoz-mcp-server",
      "args": [],
      "env": {
        "SIGNOZ_URL": "https://your-signoz-instance.com",
        "SIGNOZ_API_KEY": "your-api-key"
      }
    }
  }
}
```

## What you can ask

- "Show me all active alerts"
- "What is the p99 latency for the checkout service in the last hour?"
- "Search error logs for the payment service"
- "Create a dashboard with CPU and memory metrics"
- "List all services with traces from the last 6 hours"
