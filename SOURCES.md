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
| `sources/latexlaw` | [anoduck/LatexLaw](https://github.com/anoduck/LatexLaw) | **None (unlicensed)** | LaTeX legal/brief templates. Submodule reference only — do **not** copy out without upstream permission. |
| `sources/seriesseed-equity` | [seriesseed/equity](https://github.com/seriesseed/equity) | CC0 1.0 | Fenwick / Ted Wang Series Seed preferred-stock set. |
| `sources/cooley-seriesseed` | [CooleyLLP/seriesseed](https://github.com/CooleyLLP/seriesseed) | CC0 1.0 | Cooley fork + Series Seed Notes package. |
| `sources/bloomberg-beta-investment-documents` | [Bloomberg-Beta/Investment-Documents](https://github.com/Bloomberg-Beta/Investment-Documents) | CC BY 3.0 | Series Seed templates + SAFE side letter — attribution required. |
| `sources/beipa-balanced-employee-ip-agreement` | [github/balanced-employee-ip-agreement](https://github.com/github/balanced-employee-ip-agreement) | CC0 1.0 | Balanced Employee IP Agreement (BEIPA). |
| `sources/bonterms-mutual-nda` | [Bonterms/Mutual-NDA](https://github.com/Bonterms/Mutual-NDA) | CC BY 4.0 | Bonterms Mutual NDA — attribution required. |
| `sources/bonterms-cloud-terms` | [Bonterms/Cloud-Terms](https://github.com/Bonterms/Cloud-Terms) | CC BY 4.0 | Bonterms Cloud Terms. |
| `sources/bonterms-professional-services-agreement` | [Bonterms/Professional-Services-Agreement](https://github.com/Bonterms/Professional-Services-Agreement) | CC BY 4.0 | Bonterms PSA. |
| `sources/bonterms-data-protection-addendum` | [Bonterms/Data-Protection-Addendum](https://github.com/Bonterms/Data-Protection-Addendum) | CC BY 4.0 | Bonterms DPA. |
| `sources/bonterms-service-level-agreement` | [Bonterms/Service-Level-Agreement](https://github.com/Bonterms/Service-Level-Agreement) | CC BY 4.0 | Bonterms SLA. |
| `sources/bonterms-business-associate-agreement` | [Bonterms/Business-Associate-Agreement](https://github.com/Bonterms/Business-Associate-Agreement) | CC BY 4.0 | Bonterms BAA. |
| `sources/commonpaper-mutual-nda` | [CommonPaper/Mutual-NDA](https://github.com/CommonPaper/Mutual-NDA) | CC BY 4.0 | Common Paper Mutual NDA — attribution required. |
| `sources/commonpaper-csa` | [CommonPaper/CSA](https://github.com/CommonPaper/CSA) | CC BY 4.0 | Common Paper Cloud Service Agreement. |
| `sources/commonpaper-dpa` | [CommonPaper/DPA](https://github.com/CommonPaper/DPA) | CC BY 4.0 | Common Paper DPA. |
| `sources/commonpaper-psa` | [CommonPaper/PSA](https://github.com/CommonPaper/PSA) | CC BY 4.0 | Common Paper PSA. |
| `sources/commonpaper-sla` | [CommonPaper/SLA](https://github.com/CommonPaper/SLA) | CC BY 4.0 | Common Paper SLA. |
| `sources/commonpaper-software-license-agreement` | [CommonPaper/Software-License-Agreement](https://github.com/CommonPaper/Software-License-Agreement) | CC BY 4.0 | Common Paper Software License Agreement. |
| `sources/commonpaper-pilot-agreement` | [CommonPaper/Pilot-Agreement](https://github.com/CommonPaper/Pilot-Agreement) | CC BY 4.0 | Common Paper Pilot Agreement. |
| `sources/llc-delaware-simple` | [ParticipatoryOrgs/LLC-Delaware-Simple](https://github.com/ParticipatoryOrgs/LLC-Delaware-Simple) | CC BY 4.0 | Simple Delaware LLC OA / subscription (2015; research starting point). |
| `sources/legalmattic` | [Automattic/legalmattic](https://github.com/Automattic/legalmattic) | CC BY-SA 4.0 | Automattic / WordPress.com policies (company-docs lane). |
| `sources/basecamp-policies` | [basecamp/policies](https://github.com/basecamp/policies) | CC BY 4.0 | Basecamp handbook (archived upstream). |
| `sources/github-site-policy` | [github/site-policy](https://github.com/github/site-policy) | CC0 1.0 | GitHub site policies (company-docs lane). |
| `sources/atticus-cuad` | [The-Atticus-Project/cuad](https://github.com/The-Atticus-Project/cuad) | Research / see Atticus terms | CUAD contract-understanding dataset code. |
| `sources/atticus-maud` | [The-Atticus-Project/maud](https://github.com/The-Atticus-Project/maud) | Research / see Atticus terms | MAUD merger-agreement dataset code. |
| `sources/atticus-acord` | [TheAtticusProject/acord](https://github.com/TheAtticusProject/acord) | MIT (code) / CC BY 4.0 (dataset per README) | ACORD clause-retrieval dataset. |
| `sources/legalbench` | [HazyResearch/legalbench](https://github.com/HazyResearch/legalbench) | Per-task licenses | LegalBench legal-reasoning benchmark. |

**Not vendored as submodules (catalog link-only / no suitable mono-repo or too large to recurse):** oneNDA / oneDPA / Playbook (CC BY-ND family — product pages; email/demo gates noted in quality_notes), Y Combinator SAFE (ycombinator.com/documents), Harvey LAB (`harveyai/harvey-labs` — MIT but ~3GB task corpus; catalog-link only), Ro5s/Startup-Starter-Pack (index only, no LICENSE), commonform.org (per-form licenses; website repo), accordproject/cicero-template-library (catalog-link; engine repo is excluded), ankane/awesome-legal + opensource.legal/directory + legal-oss.com (directories only), court/government forms, FDIC P&As, Fannie DUS / Selling & Servicing Guide, CLLS UK precedents, ISDA/LMA/ACREL/AIA/ConsensusDocs/AIR CRE/REBNY paid suites.

## CC BY / attribution note

When copying material out of a CC BY or CC BY-SA submodule into another work, preserve the upstream LICENSE/NOTICE and give attribution to the named publisher (Bonterms, Common Paper, Bloomberg Beta, EasyLegalDocs, etc.). CC BY-ND works (oneNDA; Bonterms Marketplace End User Agreement) may be copied with attribution but **not** redistributed as modified versions under the original name.

## Jurisdiction-specific forms (NY / NC / Federal) — curated catalog

Court and government forms for New York, North Carolina, and the federal courts/agencies are **not** copied here. They live in a curated, source-linked catalog under [`catalog/`](catalog/README.md) — **342 entries** as of the 2026-09-29 gather + gap-fill (court/government + market-standard + premium-reference + open commercial standards + legal-AI datasets). Every URL was fetched or HTTP-verified where possible; unconfirmable direct URLs are marked `n.a.` / `null`. The catalog enforces a quality bar with explicit source tiers:

- **T1_OFFICIAL** — court/government/agency forms (authoritative, free)
- **T2_MARKET_STANDARD_PUBLIC** — SEC EDGAR, NVCA, ILPA, LSTA, Bonterms, Common Paper, oneNDA, Series Seed, Atticus/Harvey/LegalBench datasets, etc.
- **T3_PREMIUM_REFERENCE** — Blumberg, ABA model agreements, Practical Law, PLI, Bloomberg Law, Lexis/Intelligize, Deal Point Data, ISDA, LMA, ACREL, AIA, etc. (linked only, never copied)
- **EXCLUDED** — LegalZoom, RocketLawyer, AI template generators, SEO PDF mirrors (see [catalog/excluded-sources.md](catalog/excluded-sources.md))

**Hard rule:** Practical Law / Bloomberg Law / Lexis / Westlaw / Matthew Bender subscription content is never committed to this public repo. Drive-held premium packs stay on Drive; this repo is the CC0/catalog corpus.

Start at [`catalog/README.md`](catalog/README.md) for the full schema and directory map. The canonical machine-readable catalog is [`catalog/forms.yaml`](catalog/forms.yaml).

Rationale: official forms are revised frequently and redistribution terms vary by source, so the catalog indexes (form number + jurisdiction + edition/revision + official URL) rather than copying PDFs that go stale. Re-verify before filing.

> Templates are not legal advice and are not a substitute for review by a licensed
> attorney in the relevant jurisdiction.
