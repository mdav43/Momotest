---
layout: page
title: How it works
lede: "Documents are fingerprinted, sent to a shared registry, and checked against every other lender's fingerprints. No full document ever leaves your environment."
eyebrow: How it works
permalink: /how-it-works/
---

## The data flow, end to end

<div class="diagram" aria-label="Data flow diagram">
<svg viewBox="0 0 840 260" role="img" aria-labelledby="flow-title flow-desc">
  <title id="flow-title">MonetaGo Secure Financing data flow</title>
  <desc id="flow-desc">A lender hashes document data, sends the hash to the MonetaGo registry over Swift or REST, the registry checks for matches against other lenders' hashes, and returns a match signal.</desc>
  <style>
    .node { fill: #F8FAFC; stroke: #0B1F3A; stroke-width: 1.5; }
    .node-label { font-family: Inter, sans-serif; font-size: 13px; fill: #17325A; font-weight: 600; }
    .node-sub   { font-family: Inter, sans-serif; font-size: 11px; fill: #334155; }
    .edge { stroke: #0E9488; stroke-width: 1.8; fill: none; marker-end: url(#arrow); }
    .edge-label { font-family: Inter, sans-serif; font-size: 11px; fill: #0E9488; font-weight: 600; }
  </style>
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
      <path d="M0,0 L10,5 L0,10 z" fill="#0E9488"/>
    </marker>
  </defs>

  <rect class="node" x="20"  y="80"  width="170" height="100" rx="10"/>
  <text class="node-label" x="105" y="120" text-anchor="middle">Lender system</text>
  <text class="node-sub"   x="105" y="140" text-anchor="middle">Core banking or</text>
  <text class="node-sub"   x="105" y="156" text-anchor="middle">factoring platform</text>

  <rect class="node" x="230" y="80"  width="170" height="100" rx="10"/>
  <text class="node-label" x="315" y="120" text-anchor="middle">Fingerprint</text>
  <text class="node-sub"   x="315" y="140" text-anchor="middle">Hash of metadata</text>
  <text class="node-sub"   x="315" y="156" text-anchor="middle">fields, client-side</text>

  <rect class="node" x="440" y="80"  width="180" height="100" rx="10"/>
  <text class="node-label" x="530" y="120" text-anchor="middle">MonetaGo registry</text>
  <text class="node-sub"   x="530" y="140" text-anchor="middle">Confidential compute</text>
  <text class="node-sub"   x="530" y="156" text-anchor="middle">Swift API or REST</text>

  <rect class="node" x="660" y="80"  width="160" height="100" rx="10"/>
  <text class="node-label" x="740" y="120" text-anchor="middle">Match signal</text>
  <text class="node-sub"   x="740" y="140" text-anchor="middle">None / exact /</text>
  <text class="node-sub"   x="740" y="156" text-anchor="middle">partial + reason</text>

  <path class="edge" d="M190,130 L230,130"/>
  <path class="edge" d="M400,130 L440,130"/>
  <path class="edge" d="M620,130 L660,130"/>

  <text class="edge-label" x="210" y="120" text-anchor="middle">hash</text>
  <text class="edge-label" x="420" y="120" text-anchor="middle">submit</text>
  <text class="edge-label" x="640" y="120" text-anchor="middle">respond</text>
</svg>
<p class="diagram__caption">No full document crosses the boundary. Only a fingerprint and a match signal do.</p>
</div>

## Why fingerprint instead of sharing documents

Lenders won't share customer documents. Regulators won't let them. But fraud signal only exists across lenders. Fingerprinting resolves the tension:

- Each lender hashes a small number of fields before any data leaves their environment.
- The registry compares hashes, not documents.
- Partial-match logic catches altered documents without reconstructing them.

## Where the registry runs

- **Confidential compute enclaves** — matching runs inside hardware-attested TEEs so operators cannot see submissions.
- **Swift API channel** — live since 2022, the first third-party trade service on Swift.
- **Direct REST** — for participants without Swift.

## What you submit, what you get back

<dl class="kv">
  <dt>Submitted (hashed)</dt>
  <dd>Invoice number, amounts, currency, issue date, buyer, seller, asset type (invoice, BoL, air waybill, warehouse receipt, PO).</dd>
  <dt>Returned</dt>
  <dd>Match class (none / exact / partial), reason codes identifying which fields matched, a registry reference id for audit.</dd>
  <dt>Retained</dt>
  <dd>Registry metadata only. Original documents never leave your environment.</dd>
</dl>
