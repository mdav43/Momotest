---
layout: page
title: "Platform: Secure Financing"
lede: "A multi-module trade-finance operating system. Use one module or stack them. The same registry powers them all."
eyebrow: Platform
permalink: /platform/
---

## The modules

### Duplicate Detection

Checks each financing request against a shared registry of fingerprints submitted by other participating lenders.

- **Exact match** — the same document financed elsewhere.
- **Partial match** — a document that has been altered to evade exact matching. Partial match is where most fraud actually surfaces.
- **Reason codes** — which fields matched, so ops teams can triage quickly.

### Document Authentication

Independently verifies that trade documents are what they claim to be.

- **Bills of lading** authenticated against the world's largest maritime intelligence dataset.
- **Container and shipment data** cross-checked against carrier and port signals.
- **Air waybills, warehouse receipts, purchase orders** — coverage expanding by asset type.

### Registry

The shared infrastructure itself.

- **Confidential computing** — matching happens inside hardware-attested enclaves.
- **Swift API channel** — the first third-party trade service on Swift.
- **Direct REST** for fintechs and lenders without a Swift connection.

## What it costs an institution to adopt

- A small metadata payload per financing request. No full documents leave your environment.
- A pilot-scale integration in 4–6 weeks, including security review.
- Volume-based pricing. Board-level reporting included from the pilot onwards.

<p style="margin-top: var(--sp-7);">
  <a class="btn btn--primary" href="{{ '/how-it-works/' | relative_url }}">See the data flow</a>
  <a class="btn btn--ghost" href="{{ '/resources/' | relative_url }}">Read the technical brief</a>
</p>
