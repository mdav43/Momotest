---
layout: page
title: Resources
lede: "Briefings for risk, compliance, and procurement teams. Written for specialists, not for search engines."
eyebrow: Resources
permalink: /resources/
---

<ul class="resource-list" role="list">
  {% for r in site.data.resources %}
    <li>
      <a class="resource" href="{{ r.url }}">
        <span class="resource__kind">{{ r.kind }}</span>
        <h2 class="resource__title">{{ r.title }}</h2>
        <p class="resource__summary">{{ r.summary }}</p>
      </a>
    </li>
  {% endfor %}
</ul>

## FAQs

<dl class="kv" style="margin-top: var(--sp-6);">
  <dt>Where does our document data live?</dt>
  <dd>It stays with you. We receive and store fingerprints (hashes), not the original documents.</dd>

  <dt>What is the lawful basis for sharing fingerprints across lenders?</dt>
  <dd>Contractual, with customer notification built into participating lenders' terms. We can share a reference clause for your legal team.</dd>

  <dt>How long does a pilot take?</dt>
  <dd>Typically 4&ndash;6 weeks, including security review and a limited-volume phase before production cutover.</dd>

  <dt>Can we run over Swift instead of a direct REST connection?</dt>
  <dd>Yes. MonetaGo is the first third-party trade service on the Swift API channel, live since 2022.</dd>

  <dt>Do we see other lenders' data in a match?</dt>
  <dd>No. You see a match class and reason codes only.</dd>
</dl>
