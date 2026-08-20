# Legal Form Catalog — New York · North Carolina · Federal

A curated, premium-quality catalog of official and market-standard legal forms for a corporate / private-equity / securities / M&A and commercial-litigation practice spanning New York, North Carolina, and the federal courts and agencies.

**LINK ONLY.** No forms are copied into this repository. Every entry points to the publisher's own page and, where confirmable, the publisher's own document URL. Nothing paywalled or commercial is reproduced here.

## Quality bar / source tiers

- **T1_OFFICIAL:** court/government/agency forms that are authoritative and free.
- **T2_MARKET_STANDARD_PUBLIC:** SEC EDGAR filed deal exhibits, NVCA model docs, official model orders — real market precedent, free.
- **T3_PREMIUM_REFERENCE:** Blumberg, ABA model agreements, Practical Law, PLI, Bloomberg Law, Lexis/Intelligize, Deal Point Data — linked/referenced only, often paywalled; never copied.
- **EXCLUDED:** LegalZoom, RocketLawyer, AI template generators, random SEO form mirrors — not included; see [excluded-sources.md](excluded-sources.md).

## Per-entry schema

Every entry in [forms.yaml](forms.yaml) carries these fields:

- `id`
- `title`
- `jurisdiction` — `NY`, `NC`, or `Federal`
- `practice_area` — `corporate-entity-filings`, `commercial-litigation`, `appellate-litigation`, `securities-ma`, `federal-litigation`, `business-court`
- `category`
- `source_tier` — `T1_OFFICIAL`, `T2_MARKET_STANDARD_PUBLIC`, `T3_PREMIUM_REFERENCE`
- `publisher`
- `source_page_url`
- `document_url` — `null` where the research recorded "n.a."
- `form_number`
- `edition_or_revision_date`
- `access`
- `copy_policy`
- `quality_notes`
- `last_verified`

`copy_policy` values:

- `link_only` — link to the publisher; do not copy the document into this repo.
- `copy_allowed_if_license_verified` — copying permissible only after the license/terms are affirmatively verified.
- `commercial_purchase` — obtainable only by paid purchase from the publisher.
- `reference_only` — consult and cite; never copy (copyrighted and/or paywalled).

## Directory map

| File | Description |
|---|---|
| [README.md](README.md) | This file — purpose, tiers, schema, methodology, disclaimer. |
| [forms.yaml](forms.yaml) | Canonical machine-readable catalog: every entry across all jurisdictions and lanes. |
| [premium-reference-sources.md](premium-reference-sources.md) | Blumberg, ABA M&A model agreements, Practical Law, PLI PLUS, Bloomberg Law, Intelligize+ AI, Deal Point Data — reference only. |
| [excluded-sources.md](excluded-sources.md) | Exclusion policy: consumer template mills, AI template generators, SEO PDF mirrors. |
| [ny/corporate-entity-filings.md](ny/corporate-entity-filings.md) | NY Department of State entity-filing instruments (incorporation, amendment, merger, dissolution, authority, assumed name). |
| [ny/commercial-division-litigation.md](ny/commercial-division-litigation.md) | NY Supreme Court civil / Commercial Division / NYSCEF forms and model rules exhibits. |
| [ny/appellate-litigation.md](ny/appellate-litigation.md) | Appellate Division First and Second Department forms, with department-specific traps. |
| [ny/federal-litigation-sdny-edny.md](ny/federal-litigation-sdny-edny.md) | S.D.N.Y. and E.D.N.Y. civil forms, admissions, ADR, protective orders, joint local rules. |
| [nc/corporate-entity-filings.md](nc/corporate-entity-filings.md) | NC Secretary of State business-registration instruments. |
| [nc/civil-litigation-aoc.md](nc/civil-litigation-aoc.md) | NC Administrative Office of the Courts civil forms (summons, service, judgment enforcement). |
| [nc/business-court.md](nc/business-court.md) | NC Business Court rules, Notice of Designation template, eFiling guidance. |
| [nc/appellate-litigation.md](nc/appellate-litigation.md) | NC appellate rules and Appendix D formats; transcript forms; discontinued-form trap. |
| [nc/federal-litigation-ednc-mdnc-wdnc.md](nc/federal-litigation-ednc-mdnc-wdnc.md) | E.D.N.C., M.D.N.C., and W.D.N.C. civil forms and local rules. |
| [federal/sec-official-forms.md](federal/sec-official-forms.md) | SEC official forms and the eCFR primary text for schedules with no PDF. |
| [federal/securities-ma-edgar.md](federal/securities-ma-edgar.md) | How to pull deal documents from EDGAR, Item 601 exhibit conventions, curated example filings. |
| [federal/market-standard-public-models.md](federal/market-standard-public-models.md) | NVCA model venture-financing and PIPE documents. |

## Verification methodology

Every catalog entry is source-linked to an official or premium-reference publisher. URLs were fetched or HTTP-verified where possible; New York court pages behind bot protection are documented with their verification method (snapshot-confirmed or live-page-confirmed) in the relevant lane files, and unconfirmable direct document URLs are marked `n.a.` or preserved as official-page `href` values with caveats. **`n.a.` means the value was not confirmable from a fetched official page — it is never a guess.** Where a direct document URL could not be confirmed, the stable official index page is given instead.

Two access constraints shaped the New York rows: `www.nycourts.gov` and `ww2.nycourts.gov` sit behind Cloudflare bot protection and robots restrictions, so several court URLs were verified either by fetching the open NYSCEF/UCS document host `iappscontent.courts.state.ny.us` or by extracting live `href` values from archived snapshots of the official nycourts.gov pages plus a live screenshot confirming the current page still exists. Those rows say so in their quality notes. On the federal side, eCFR intermittently rate-limits automated requests, and `efts.sec.gov` is robots-blocked to automated HTML fetchers.

**Re-verify before filing.** Court and agency sites revise forms, re-version filenames, and move assets (nccourts.gov in particular uses unstable asset filenames and `VersionId` query strings). Always re-resolve a form from its landing page before relying on a stored deep link.

## Disclaimer

Templates, forms, and links in this catalog are provided for informational and research purposes only. They are **not legal advice**, do not create an attorney-client relationship, and are no substitute for independent verification of the current official form, the governing rules, and the requirements of the specific court, agency, or transaction.
