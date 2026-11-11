---
name: care-business-overview
description: For people who run a care business on VidaKind - read their own company's upcoming visits, client list and team. Use when an operator or office admin asks "what's on this week", "who's working tomorrow", "how many clients do we have", or similar about their own VidaKind company.
---

# Your care business on VidaKind, at a glance

For owners and office admins of a care business that runs on VidaKind. This skill uses the connector's `list_company_visits`, `list_company_clients` and `list_company_team` tools. They are read-only: nothing is created, changed or deleted.

## Which company

The tools work for logins that are an office admin of a VidaKind company. If the login belongs to more than one company, a tool answers with `needsCompany` and the list of Company IDs: ask which one, then call again with `company`.

If a tool says there is no company access, explain that this account isn't an office admin of a business on VidaKind, and that families should use the `find-carers` and `check-my-care` skills instead.

## Visits

Call `list_company_visits`, with `from` as `YYYY-MM-DD` for the first day wanted (for example today, or the start of next week). Summarise by day: client, start time, hours, carer and status. Point out visits that have no carer yet.

## Clients and team

`list_company_clients` gives client names, suburbs and statuses. `list_company_team` gives team names, roles and whether each is active. Use them to answer counts and simple questions ("which clients are in Southport?", "who is active?").

## Limits

These lists exclude prices, pay, contact details, notes and health information, and show up to 200 rows. For anything else, or to make a change, the person uses the VidaKind portal at portal.vidakind.com. Don't guess at information the tools don't return.
