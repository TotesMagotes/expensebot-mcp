# Install ExpenseBot MCP

Prefer the hosted Streamable HTTP server with OAuth:

```json
{
  "mcpServers": {
    "expensebot": {
      "url": "https://mcp.expensebot.ai/mcp"
    }
  }
}
```

After adding the server, open the authorization URL, sign in to ExpenseBot, and approve access. Do not ask the user to paste a token into the conversation.

If the host supports only local stdio MCP, configure:

```json
{
  "mcpServers": {
    "expensebot": {
      "command": "npx",
      "args": ["-y", "@expensebot/mcp-server-auth"],
      "env": {
        "EXPENSEBOT_TOKEN": "${env:EXPENSEBOT_TOKEN}"
      }
    }
  }
}
```

The token must be stored in the host's environment or secret manager. Never place it in command arguments, documentation, email, or chat.

Verify installation by listing tools and confirming that ExpenseBot exposes its expense search and Gmail scan tools. Full setup guidance is at <https://www.expensebot.ai/mcp>.
