# Weather MCP Demo

## Setup

### 1. Create and activate virtual environment

```bash
uv venv
source .venv/bin/activate
```

### 2. Install dependencies

```bash
uv pip install -r requirements.txt
```

## Using with Claude Desktop

### Option 1: Using `mcp install` (Recommended)

The easiest way to set up the weather MCP server with Claude Desktop is using the `mcp install` command:

```bash
# Make sure you're in the project directory
cd /path/to/mcp-demo

# Install the weather MCP server to Claude Desktop
mcp install weather
```

This will automatically register the weather server with Claude Desktop.

### Option 2: Manual Configuration

Alternatively, you can manually edit Claude's desktop config file located at:

```
~/Library/Application Support/Claude/claude_desktop_config.json
```

Add your server in the `mcpServers` key:

```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "/ABSOLUTE/PATH/TO/mcp-demo/weather",
        "run",
        "weather.py"
      ]
    }
  }
}
```

> **Note**: Replace `/ABSOLUTE/PATH/TO/mcp-demo` with the actual absolute path to your project directory.

## Running the MCP Server Manually

If you want to run the server manually (not recommended for Claude Desktop integration):

```bash
uv run weather/weather.py
```

## Using the Weather Tools

Once configured, you can ask Claude about weather information using:

1. **Get Weather Alerts**: Ask about weather alerts for a US state
   - Example: "What are the current weather alerts in CA?"

2. **Get Weather Forecast**: Ask about weather forecast for a specific location
   - Example: "What's the weather forecast for San Francisco? The coordinates are latitude 37.7749, longitude -122.4194."
