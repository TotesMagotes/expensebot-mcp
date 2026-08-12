# ExpenseBot MCP

Public installation and discovery metadata for the hosted ExpenseBot Model Context Protocol server.

ExpenseBot gives AI assistants and automation platforms structured access to expense data, Gmail receipt capture, reports, income, mileage, compliance checks, and accounting handoffs. ExpenseBot remains the system that captures and organizes receipts; downstream accounting software remains the source of truth for the books.

## Recommended: remote OAuth

Use the hosted Streamable HTTP endpoint in clients that support remote MCP and OAuth:

```text
https://mcp.expensebot.ai/mcp
```

Example `mcp.json`:

```json
{
  "mcpServers": {
    "expensebot": {
      "url": "https://mcp.expensebot.ai/mcp"
    }
  }
}
```

The client should open ExpenseBot sign-in and consent in the browser. Do not paste an ExpenseBot token into chat.

## Local stdio fallback

Clients without remote OAuth support can run the public npm adapter:

```text
npx -y @expensebot/mcp-server-auth
```

Store a revocable ExpenseBot token in the client's `EXPENSEBOT_TOKEN` environment or secret configuration. Generate and revoke tokens from [AI Assistant Tokens](https://www.expensebot.ai/process-info?openMcpTokens=true&source=github).

## What agents can do

- Search and analyze expenses, income, mileage, subscriptions, and profit and loss.
- Submit receipt images and PDFs and check processing results.
- Scan connected Gmail accounts for receipts and monitor scan progress.
- Add cash expenses, mileage, income, and confirmed client advances.
- Review, correct, categorize, group, and annotate exact expenses with confirmation safeguards.
- Create, inspect, export, and share reports and continue into client billing.
- Review credits, refunds, compliance issues, monthly books, and client advance balances.
- Trace document activity and open the relevant ExpenseBot review UI when a visual workflow is safer.

The live server currently exposes more than 50 tools. Write actions use previews, confirmations, bounded selections, or app handoffs where appropriate.

## Useful prompts

- `Scan Gmail for new receipts and tell me what needs attention.`
- `Show me my unsubmitted travel expenses from last month.`
- `Group my Toronto Uber Eats expenses from this quarter under Client Demo, then create a report without personal expenses and help me bill the client.`
- `How much of Client Acme's advance remains?`
- `Compare this quarter's spending with the same quarter last year.`

## Documentation and support

- Setup guide: <https://www.expensebot.ai/mcp>
- Practical prompt guide: <https://www.expensebot.ai/mcp-actions>
- Privacy: <https://www.expensebot.ai/privacy>
- Support: <mailto:support@expensebot.ai>

This repository intentionally contains public installation metadata only. The hosted ExpenseBot application and its private source code are not published here.
