---
name: agencyhandy
description: Use when the user asks about their Agency Handy workspace — clients, leads, projects, tasks, tickets, invoices, proposals, orders, services, cash flow or client health — or wants to create or update any of them.
---

# Agency Handy

The `agencyhandy` MCP server is connected to the user's Agency Handy workspace. Its tools start with `ah_`.

## Start of a session

1. Call `ah_health` once to confirm the API key works and see which workspace you are in.
2. Read the `ah://full-context` resource before your first non-trivial question. It explains the data model, field names and workflows.

## Reading

- Prefer the `*_context` tools (`ah_project_context`, `ah_task_context`, `ah_ticket_context`, `ah_invoice_context`, `ah_proposal_context`, `ah_order_context`). They return the record together with its members, comments and related items in one call.
- For owner-level questions, use `ah_dashboard_digest`, `ah_cash_risk` and `ah_client_churn_risk`.
- To turn a name into an id, use `ah_member_resolve` or `ah_status_resolve` instead of guessing.

## Writing

Write tools change live customer data and some of them email clients: `ah_invoice_send`, `ah_proposal_send` and `ah_client_invite`.

- Before calling any create, update, send or delete tool, tell the user exactly what will change and get confirmation.
- Never send an invoice or proposal, or invite a client, unless the user explicitly asked for that.
- After a write, read the record back and report what actually changed.
