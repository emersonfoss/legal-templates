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

## Jurisdiction-specific forms (NY / NC) — index, don't copy

Court and government forms for New York and North Carolina are **not** vendored here.
They are publicly available on official catalogs but redistribution terms vary by
source and the forms are revised frequently. The intended approach is a pointer/index
layer (form number, jurisdiction, category, edition/revision date, official URL)
rather than copying PDFs that go stale.

- **New York** — [NYSCEF forms](https://iappscontent.courts.state.ny.us/nyscef/live/forms.htm),
  [CourtHelp DIY forms](https://ww2.nycourts.gov/courts/11jd/supreme/civilterm/court_help_forms.shtml),
  [Civil Court forms](https://ww2.nycourts.gov/courts/nyc/civil/forms.shtml),
  [Appellate Division forms](https://www.nycourts.gov/courts/ad2/appellateterm_forms.shtml),
  [Justia NY](https://forms.justia.com/new-york/),
  [Clio NY templates](https://www.clio.com/legal-templates/new-york/).
- **North Carolina** — [NC Judicial Branch AOC forms](https://www.nccourts.gov/documents/forms)
  (1,120+ fillable PDFs: AOC-CV civil, AOC-CR criminal, AOC-E estate/probate, family),
  [LawHelpNC](https://www.lawhelpnc.org/online-legal-forms),
  [Middle District of NC federal forms](https://www.ncmd.uscourts.gov/forms).

> Templates are not legal advice and are not a substitute for review by a licensed
> attorney in the relevant jurisdiction.
