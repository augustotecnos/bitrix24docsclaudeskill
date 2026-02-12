# Bitrix24 REST API Documentation Project

## Overview
This project contains the complete Bitrix24 REST API documentation (1036 pages) split into 52 semantically organized markdown files in the `docs/` directory.

## How to Find Documentation

1. **Start with the index**: Read `docs/_index.md` to find which file covers your topic
2. **Use Grep** to search for specific API method names (e.g., `crm.lead.add`)
3. **Use Glob** with `docs/api-crm-*.md` to find CRM-related documentation
4. **Each file has YAML frontmatter** with `methods` list and `description`

## File Naming Convention
- `api-crm-{entity}.md` — CRM entity API reference (leads, contacts, deals, etc.)
- `api-crm-universal-{topic}.md` — Universal CRM API (works with any entity type)
- `api-crm-timeline-{topic}.md` — Timeline and activities
- `api-{module}.md` — Non-CRM API modules (bizproc, widgets, events, ai)
- `tutorials-{topic}.md` — Step-by-step usage tutorials
- `settings-{topic}.md` — Configuration and authentication
- `sdk-bx24-js.md` — JavaScript SDK

## Quick File Lookup

### When working with CRM entities:
- Leads → `docs/api-crm-leads.md`
- Contacts → `docs/api-crm-contacts.md` + `docs/api-crm-contacts-fields.md`
- Companies → `docs/api-crm-companies.md`
- Deals → `docs/api-crm-deals.md` + `docs/api-crm-deals-recurring.md`
- Quotes → `docs/api-crm-quote.md`
- Universal/SPA → `docs/api-crm-universal-items.md`

### When working with CRM configuration:
- Stages/Statuses → `docs/api-crm-status.md`
- User fields, categories → `docs/api-crm-universal-config.md`
- Payments, orders → `docs/api-crm-universal-commerce.md`
- Requisites → `docs/api-crm-requisites.md`

### When working with automation/integration:
- Business processes → `docs/api-bizproc.md`
- Events/webhooks → `docs/api-events.md`
- Widgets/embedding → `docs/api-widgets.md`
- Auth/OAuth → `docs/settings-auth.md`

## Important Notes
- Documentation language: English (translated from Bitrix24 official docs)
- Source: https://apidocs.bitrix24.com
- Files marked "outdated" contain deprecated APIs still in use by legacy code
- `docs/_manifest.json` has structured metadata for programmatic access
