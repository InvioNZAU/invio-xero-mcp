# Invio Xero MCP

Every Xero organisation you run, in one AI session. Writes wait for a person to approve them.

This repository holds documentation only. Invio Xero MCP is a hosted, closed-source service, so there is no server code here to install or run.

- Website: https://www.invio.co.nz/xero-mcp
- Australia: https://www.invio.com.au/xero-mcp
- Setup guide: https://www.invio.co.nz/guides/xero-mcp-setup
- Security: https://www.invio.co.nz/xero-mcp/security
- Official MCP Registry: `nz.co.invio/xero`

## What it does

**Reading is immediate.** Your assistant can list organisations, invoices and bills with line items, contacts, credit notes, quotes, projects, the chart of accounts, and Profit and Loss and Balance Sheet reports. Read-only payroll is an optional permission, off by default.

**Writing is never immediate.** Every new or changed invoice, bill, contact, credit note, quote or manual journal becomes a draft in an approval queue showing the organisation and the exact payload. Nothing reaches Xero until a person approves it, and each approval is recorded against the person who made it. Unapproved drafts expire after 24 hours. Recording payments and payroll changes are separate permissions, off by default.

The server exposes 38 tools. Invio does not keep a copy of your ledger; results are read from Xero on request. You can revoke a connector or disconnect Xero at any time from Settings.

## Connect

1. In Invio, open Settings > AI connections, then the MCP tab, and choose Xero.
2. Pick your permissions, click "Connect Xero" and allow access on Xero's own screen, one organisation at a time. Use "Connect another" for the next one.
3. Click "Generate connector URL" and copy it straight away. It is shown only once.
4. Add the URL to Claude, ChatGPT or Microsoft Copilot as a custom connector. The setup guide has the steps and plan requirements for each client.

Clients that send headers can use the fixed endpoint. The key is the last part of your connector URL, with no prefix. The exact config format depends on the client.

```json
{
  "mcpServers": {
    "invio-xero": {
      "url": "https://www.invio.co.nz/api/xero-mcp",
      "headers": { "X-API-Key": "YOUR_INVIO_CONNECTOR_KEY" }
    }
  }
}
```

Transport: Streamable HTTP. There is a 7-day free trial, no card needed.

## Independence

Invio is an independent connector built on Xero's official API. It works with Xero and is not affiliated with, endorsed by or certified by Xero. Xero is a trademark of Xero Limited. Claude, ChatGPT and Microsoft Copilot are trademarks of their respective owners.
