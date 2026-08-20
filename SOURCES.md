# Sources & Attribution

This repository aggregates attorney-drafted and open-source legal templates from
multiple upstream sources. The base collection is forked from
[General-Legal/legal-templates](https://github.com/General-Legal/legal-templates)
(CC0 1.0 — public domain, no attribution required, though provenance is preserved here).

Additional open-source template collections are vendored as **git submodules** under
[`sources/`](./sources). Submodules pin a specific upstream commit and preserve each
project's own license file — they are referenced, not re-licensed. Update a vendored
collection with `git submodule update --remote sources/<name>`.

## Vendored collections

| Submodule | Upstream | License | Notes |
|---|---|---|---|
| `sources/open-source-legal-engineering` | [ErichDylus/Open-Source-Legal-Engineering](https://github.com/ErichDylus/Open-Source-Legal-Engineering) | MIT | Open-source legal templates + scripts (some web3/crypto tilt). Preserve LICENSE + NOTICE if copying code out. |
| `sources/easylegaldocs-templates` | [EasyLegalDocs/legal-templates](https://github.com/EasyLegalDocs/legal-templates) | CC BY-SA 4.0 | Broad template library. Share-Alike + attribution required for derivatives of these templates. |
| `sources/ugovor-contract-template` | [neuralab/ugovor-contract-template](https://github.com/neuralab/ugovor-contract-template) | MIT | Service-based production contract templates. |
| `sources/latexlaw` | [anoduck/LatexLaw](https://github.com/anoduck/LatexLaw) | **None (unlicensed)** | LaTeX legal/brief templates. Included as a submodule reference only — no license file means default copyright reserves all rights; do **not** copy code out of this submodule without upstream permission. |

## Jurisdiction-specific forms (NY / NC / Federal) — curated catalog

Court and government forms for New York, North Carolina, and the federal courts/agencies are **not** copied here. They live in a curated, source-linked catalog under [`catalog/`](catalog/README.md) — 179 entries across NY, NC, and Federal, every URL fetched or HTTP-verified where possible (NY court pages behind bot protection are snapshot/live-page-confirmed; unconfirmable direct URLs marked `n.a.`). The catalog enforces a quality bar with explicit source tiers:

- **T1_OFFICIAL** — court/government/agency forms (authoritative, free)
- **T2_MARKET_STANDARD_PUBLIC** — SEC EDGAR filed deal exhibits, NVCA model docs, official model orders
- **T3_PREMIUM_REFERENCE** — Blumberg, ABA model agreements, Practical Law, PLI, Bloomberg Law, Lexis/Intelligize, Deal Point Data (linked only, never copied)
- **EXCLUDED** — LegalZoom, RocketLawyer, AI template generators, SEO PDF mirrors (see [catalog/excluded-sources.md](catalog/excluded-sources.md))

Start at [`catalog/README.md`](catalog/README.md) for the full schema and directory map. The canonical machine-readable catalog is [`catalog/forms.yaml`](catalog/forms.yaml). Lanes: NY (DOS entity filings, Commercial Division/NYSCEF litigation, AD1/AD2 appellate, SDNY/EDNY federal), NC (SOS entity filings, AOC civil litigation, Business Court, appellate, EDNC/MDNC/WDNC federal), Federal (SEC official forms, EDGAR deal precedent, NVCA models).

Rationale: official forms are revised frequently and redistribution terms vary by source, so the catalog indexes (form number + jurisdiction + edition/revision + official URL) rather than copying PDFs that go stale. Re-verify before filing.

> Templates are not legal advice and are not a substitute for review by a licensed
> attorney in the relevant jurisdiction.
