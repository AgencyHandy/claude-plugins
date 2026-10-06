# Agency Handy plugins for Claude Code

Connect Claude Code to your Agency Handy workspace. Ask about clients, projects, tasks, tickets, invoices and proposals, or create and update them, without leaving your terminal.

## Install

```
/plugin marketplace add AgencyHandy/claude-plugins
/plugin install agencyhandy@agencyhandy
```

Claude Code will ask for your **Agency Handy API key**. You can find it in Agency Handy under **Settings → Workspace Config → API Key**. The key is stored in your system keychain.

To change the key later, run `/plugin configure agencyhandy@agencyhandy` in Claude Code.

## What you get

- **The `agencyhandy` MCP server** (`https://mcp.agencyhandy.com/`): about 100 `ah_*` tools covering clients, leads, projects, tasks, tickets, invoices, proposals, orders, services, custom fields and webhooks, plus owner insights such as cash risk and client churn risk.
- **The `agencyhandy` skill**, which teaches Claude how to use these tools well.
- **A confirmation guard.** Claude Code always asks you before it runs any tool that emails your clients, changes an invoice's status, or deletes data: sending invoices and proposals, inviting or creating clients (which sends an invite email), converting leads, setting invoice status, and deleting custom fields. This holds in every permission mode, including auto mode.

## Try it

- "What's overdue across my projects this week?"
- "Which clients are at risk of churning?"
- "Create a task in the Acme website project for Sara, due Friday."
- "Summarize ticket 1234 and draft a reply."

## Security

The API key acts as you, with your role's permissions in that workspace. Anything you can do in Agency Handy, Claude can do through this plugin. Actions that reach your clients or delete data always stop for your confirmation. Other changes, such as creating a task, follow your normal Claude Code permission settings.

To revoke access, delete the key in Agency Handy under **Settings → Workspace Config → API Key**.

## Development

The plugin ships an eval suite in `plugins/agencyhandy/evals/`. It runs against mocked Agency Handy responses, so it never touches real data:

```
cd plugins/agencyhandy
claude plugin eval . --ablation none --threshold 1
```

## Support

support@agencyhandy.com
