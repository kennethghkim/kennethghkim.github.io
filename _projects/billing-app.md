---
title: "Customer Billing & Usage Management Application"
order: 1
context: "Internal project at ColorInfoTech"
period: "May 2026 – Jun 2026"
summary: "Designed an in-house billing application and directed AI coding agents to build it, automating statements for 168 accounts and cutting preparation time by 67%."
description: "Designed an in-house billing application and directed AI coding agents to build it, automating statements for 168 accounts and cutting preparation time by 67%."
role:
  - "Did the billing by hand first, finding rules kept in staff memory and formulas"
  - "Separated real contract rules from layout noise and made tax, device totals, and exclusions optional"
  - "Automated only repeatable steps, leaving 29 special-format accounts and judgment calls to staff"
  - 'Designed around one source of truth, then directed AI agents under <a href="/projects/simpleharness/">simpleharness</a> with cross-agent review'
  - "Reworked the model when device exclusions surfaced mid-build, then validated it with Business Support teammates"
---

## Results

- 168 of 197 accounts automated; the other 29 need client-specific formats
- Preparation time: 15 → 5 minutes per account (−67%), about 20 hours saved per month
- 312 automated tests; an independent calculation matched all 1,501 customer-month cases
- Zero change in billed totals after the database redesign, checked against every past billing month
- Fixed a bug that could erase other months' settings before any data was lost; cross-agent review caught what a single audit missed
- Used for June–August billing and handed over to 2 trained users

## How the Application Works

```mermaid
flowchart LR
    ui["<b>Desktop app</b><br/>settings · live preview"]
    db[("<b>SQLite</b><br/>contracts · readings")]
    engine["<b>Billing engine</b><br/>terms as rules"]
    doc["<b>Document model</b>"]
    out["<b>Preview · PDF · Excel</b>"]
    ui <--> db --> engine --> doc --> out
```

## Screens

<p class="project-note">Shown with ColorInfoTech's permission. Fictional data and masked company details; English labels added for this page.</p>

<div class="project-gallery">
  <figure>
    <a href="/images/projects/billing-app/editor.png"><img src="/images/projects/billing-app/editor.png" alt="Issuance editor with contract settings on the left and a live statement preview on the right"></a>
    <figcaption>Issuance editor: contract settings on the left, live statement preview on the right.</figcaption>
  </figure>
  <figure>
    <a href="/images/projects/billing-app/pricing-settings.png"><img src="/images/projects/billing-app/pricing-settings.png" alt="Per-device pricing settings"></a>
    <figcaption>Per-device pricing: base fee, included pages, and excess rate for each counter.</figcaption>
  </figure>
  <figure>
    <a href="/images/projects/billing-app/aggregate-settings.png"><img src="/images/projects/billing-app/aggregate-settings.png" alt="Aggregate plan settings next to the aggregate block of the statement"></a>
    <figcaption>Shared allowance across two devices: excess usage is billed once, in the aggregate block.</figcaption>
  </figure>
  <figure>
    <a href="/images/projects/billing-app/statement.png"><img src="/images/projects/billing-app/statement.png" alt="Generated monthly usage statement for a fictional client"></a>
    <figcaption>Generated monthly statement for a fictional client.</figcaption>
  </figure>
  <figure>
    <a href="/images/projects/billing-app/customer-list.png"><img src="/images/projects/billing-app/customer-list.png" alt="Client list with fictional data"></a>
    <figcaption>Client list with the latest meter reading month.</figcaption>
  </figure>
</div>
