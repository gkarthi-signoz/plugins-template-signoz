# SigNoz MCP Plugin

Connects Cursor to the [SigNoz MCP server](https://github.com/SigNoz/signoz-mcp-server) so you can query metrics, traces, logs, alerts, and dashboards using natural language.

## Setup

### 1. Find your region

Open SigNoz and go to **Settings > Ingestion**. Your region is shown in the endpoint URL:

| Endpoint contains | Region |
|---|---|
| `ingest.us.signoz.cloud` | `us` |
| `ingest.eu.signoz.cloud` | `eu` |
| `ingest.in.signoz.cloud` | `in` |

### 2. Add the plugin to Cursor

Click **Add to Cursor** on the plugin page, then click **Open Cursor** in the browser prompt.

### 3. Install the MCP server

Cursor will open an **Install MCP Server?** dialog. In the URL field, replace `{SIGNOZ_REGION}` with your region from step 1 (e.g. `us`, `eu`, or `in`), then click **Install**.

### 4. Authenticate

Once the plugin is installed, click **Connect** in Cursor's MCP panel. This opens the authorization flow: enter your SigNoz instance URL and API key when prompted.

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
