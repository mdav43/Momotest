---
layout: solution
title: "Screen every financing request against a shared registry"
audience: "Banks and NBFIs"
lede: "Detect exact and partial duplicate financing across lenders before you disburse. Integrate over the Swift API or a direct REST connection."
permalink: /solutions/banks-nbfis/
---

## What you get

- **Duplicate detection** against a registry shared by 20+ international banks.
- **Document authentication** for bills of lading, using a maritime intelligence partner as an independent source of truth.
- **Exact and partial match** results — including matches where a fraudster has altered fields to evade detection.
- **Swift API channel** — the first third-party trade service to operate over Swift, so you do not need a new vendor connection.
- **Confidential computing** so no lender sees another lender's documents. Only the match signal crosses the boundary.

## How your team uses it

1. A financing request lands with your trade ops or credit team.
2. Your core banking or trade-finance platform sends a small metadata payload to MonetaGo — either over Swift or REST.
3. MonetaGo returns a signal: no match, exact duplicate, or partial duplicate. Latency is sub-second.
4. If duplicate, your ops team can hold and investigate before disbursement.

## Integration options

<dl class="kv">
  <dt>Swift API</dt>
  <dd>Use your existing Swift connection. MonetaGo is the first third-party trade service on Swift's API channel (live 2022).</dd>
  <dt>Direct REST</dt>
  <dd>TLS, mTLS, OAuth2 client credentials. Typical pilot integration: 4–6 weeks including security review.</dd>
  <dt>Core system bundles</dt>
  <dd>Pre-integrated with partner platforms including efcom for factoring operations.</dd>
</dl>

## Why banks have adopted it

- Duplicate financing is invisible inside a single bank's four walls. A cross-institution registry is the only way to see it.
- No customer data leaves your environment in clear text — we fingerprint documents client-side.
- Regulator-aligned: underpins the ICC UK C4DTI "Shutting fraudsters out of trade" workstream.
