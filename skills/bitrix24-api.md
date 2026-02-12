---
description: |
  Bitrix24 REST API documentation reference. Use this skill when the user asks about Bitrix24 API methods, CRM entities (leads, contacts, deals, companies, quotes), webhooks, OAuth authentication, widgets, business processes, or any Bitrix24 integration topic. Triggers on mentions of: "bitrix24", "bitrix", "crm.lead", "crm.deal", "crm.contact", "crm.company", "crm.item", "bizproc", "BX24", "bx24.js", "placement", "bitrix api", "bitrix webhook".
---

# Bitrix24 REST API Reference

You have access to the complete Bitrix24 REST API documentation (1036 pages across 54 files) located at `${CLAUDE_PLUGIN_ROOT}/docs/`.

## How to Find Information

### Step 1: Identify the right file

Use this quick lookup to find the correct documentation file:

**Getting Started:**
- API overview and capabilities → `${CLAUDE_PLUGIN_ROOT}/docs/00-overview.md`
- First steps, error codes, limits → `${CLAUDE_PLUGIN_ROOT}/docs/01-getting-started.md`
- Full documentation index → `${CLAUDE_PLUGIN_ROOT}/docs/_index.md`

**CRM Core Entities:**
- Leads → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-leads.md`
- Contacts → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-contacts.md` + `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-contacts-fields.md`
- Companies → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-companies.md`
- Deals → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-deals.md` + `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-deals-recurring.md`
- Quotes → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-quote.md`
- Universal/SPA items → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-universal-items.md`

**CRM Configuration:**
- Stages/Statuses → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-status.md`
- User fields, categories, SPA types → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-universal-config.md`
- Payments, orders, product rows → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-universal-commerce.md`
- Requisites → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-requisites.md` + `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-requisites-presets.md`
- Currency → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-currency.md`
- Document generator → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-document-generator.md`
- Automation/Triggers → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-automation.md`
- Enumerations, multifields, duplicates → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-auxiliary.md`

**CRM Timeline & Activities:**
- Activities (base, todo, badges) → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-timeline-activities.md`
- Activity configuration → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-timeline-activities-config.md`
- Log messages, icons, logos → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-timeline-logmessage.md`
- Comments, notes, layout blocks → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-timeline-other.md`

**Other APIs:**
- Business processes → `${CLAUDE_PLUGIN_ROOT}/docs/api-bizproc.md`
- Events/webhooks → `${CLAUDE_PLUGIN_ROOT}/docs/api-events.md`
- Widgets (core) → `${CLAUDE_PLUGIN_ROOT}/docs/api-widgets.md`
- Widgets (CRM placements) → `${CLAUDE_PLUGIN_ROOT}/docs/api-widgets-crm.md`
- Widgets (UI interaction) → `${CLAUDE_PLUGIN_ROOT}/docs/api-widgets-ui.md`
- AI integration → `${CLAUDE_PLUGIN_ROOT}/docs/api-ai.md`
- BI Connector → `${CLAUDE_PLUGIN_ROOT}/docs/api-biconnector.md`
- Tasks v3 → `${CLAUDE_PLUGIN_ROOT}/docs/api-tasks-v3.md`
- Common/System → `${CLAUDE_PLUGIN_ROOT}/docs/api-common-system.md`
- Vibe/Social → `${CLAUDE_PLUGIN_ROOT}/docs/api-vibe.md`
- Document Generator (general) → `${CLAUDE_PLUGIN_ROOT}/docs/api-document-generator.md`
- Miscellaneous endpoints → `${CLAUDE_PLUGIN_ROOT}/docs/api-misc.md`
- Other miscellaneous → `${CLAUDE_PLUGIN_ROOT}/docs/misc.md`

**Configuration & Auth:**
- OAuth, tokens, app installation → `${CLAUDE_PLUGIN_ROOT}/docs/settings-auth.md`
- API call settings, performance, limits → `${CLAUDE_PLUGIN_ROOT}/docs/settings-api-calls.md`
- BX24 JavaScript SDK → `${CLAUDE_PLUGIN_ROOT}/docs/sdk-bx24-js.md`
- Marketplace publishing → `${CLAUDE_PLUGIN_ROOT}/docs/market-publishing.md`
- Local integrations → `${CLAUDE_PLUGIN_ROOT}/docs/local-integrations.md`

**Tutorials:**
- Adding CRM objects → `${CLAUDE_PLUGIN_ROOT}/docs/tutorials-crm-add.md`
- Editing CRM objects → `${CLAUDE_PLUGIN_ROOT}/docs/tutorials-crm-edit.md`
- Getting/listing CRM data → `${CLAUDE_PLUGIN_ROOT}/docs/tutorials-crm-get.md`
- Other CRM operations → `${CLAUDE_PLUGIN_ROOT}/docs/tutorials-crm-other.md`
- Business process tutorials → `${CLAUDE_PLUGIN_ROOT}/docs/tutorials-bizproc.md`
- Tasks tutorials → `${CLAUDE_PLUGIN_ROOT}/docs/tutorials-tasks.md`
- Other tutorials (sales, bots, telephony) → `${CLAUDE_PLUGIN_ROOT}/docs/tutorials-other.md`

**Deprecated (still used by legacy code):**
- Old Invoice API → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-outdated-invoice.md`
- Old Products/Catalog API → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-outdated-products.md`
- Old misc (VAT, measures, categories) → `${CLAUDE_PLUGIN_ROOT}/docs/api-crm-outdated-misc.md`

### Step 2: Search for specific methods

If the user asks about a specific API method (e.g., `crm.lead.add`), use Grep to search across all docs:

```
Grep pattern="crm\.lead\.add" path="${CLAUDE_PLUGIN_ROOT}/docs/"
```

Each file has YAML frontmatter with a `methods` list. You can search frontmatter to find which file documents a method:

```
Grep pattern="crm\.lead\.add" path="${CLAUDE_PLUGIN_ROOT}/docs/" glob="*.md"
```

### Step 3: Read the relevant section

Once you find the right file, use Read to get the content. For large files, use Grep first to find the relevant section, then Read with offset/limit to get just that part.

## Response Guidelines

When answering Bitrix24 API questions:

1. **Always cite the source file** so the user knows where to find more details
2. **Include working code examples** from the documentation when available
3. **Mention required scopes** if the documentation specifies them
4. **Note if an API is deprecated** and suggest the modern alternative
5. **Include parameter tables** when documenting a specific method
6. **Mention rate limits** from `settings-api-calls.md` when relevant

## Important Notes

- Documentation language: English (translated from Bitrix24 official docs)
- Source: https://apidocs.bitrix24.com
- The `crm.item.*` universal API works with any entity type and is the recommended modern approach
- Files prefixed with `api-crm-outdated-*` contain deprecated APIs
