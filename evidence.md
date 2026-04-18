---
layout: page
title: Evidence
lede: "Who uses MonetaGo, what they say about it, and what the numbers look like."
eyebrow: Evidence
permalink: /evidence/
---

## By the numbers

{% include stat-grid.html %}

## Named institutions

<ul class="customer-strip" role="list" style="margin-top: var(--sp-5);">
  {% for c in site.data.customers.institutions %}
    <li class="customer-strip__item">{{ c.name }} &mdash; <span style="font-weight: 400;">{{ c.kind }}</span></li>
  {% endfor %}
</ul>

## What customers have said

<div class="grid grid--2" style="margin-top: var(--sp-6);">
  {% for q in site.data.customers.quotes %}
    <figure class="quote">
      <blockquote class="quote__text">&ldquo;{{ q.quote }}&rdquo;</blockquote>
      <figcaption class="quote__attr">
        <span class="quote__name">{{ q.name }}</span> &middot; {{ q.role }}, {{ q.org }}
      </figcaption>
    </figure>
  {% endfor %}
</div>

## Independent references

- **Swift** — MonetaGo is the first third-party trade service on the Swift API channel.
- **ICC United Kingdom** — the registry underpins the C4DTI "Shutting fraudsters out of trade" workstream.
- **Trade press** — coverage in Global Trade Review, Trade Finance Global, PYMNTS.

## Case studies

We publish a small number of detailed case studies under NDA on request. They cover:

- A global bank rolling out duplicate detection across three regions in a single quarter.
- A factoring platform integrating fraud screening into an existing credit pipeline.
- A national trade body sponsoring a cohort of lenders through a shared contract.

<p style="margin-top: var(--sp-6);">
  <a class="btn btn--primary" href="mailto:{{ site.contact.email }}?subject=Case%20studies">Request a case study</a>
</p>
