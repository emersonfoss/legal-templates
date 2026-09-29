# Excluded Sources

This catalog is built for professional corporate/PE/securities/M&A and commercial-litigation work, so consumer template mills and machine-generated form sites are excluded on quality grounds, not merely on licensing grounds. LegalZoom, RocketLawyer, and AI template generators produce generic, "eighth-grade"-level documents that are not tailored to New York, North Carolina, or federal practice, do not track the governing statutes, court rules, local rules, or Regulation S-K conventions, and are unsuitable for M&A, securities, or litigation filings. Random SEO PDF mirrors of official forms are excluded for a related reason: they go stale, they strip revision codes, and they cannot be relied on to be the current official edition. Where such a mirror exists, this catalog links the official publisher instead — `dos.ny.gov`, `iappscontent.courts.state.ny.us`, `nycourts.gov`, `sosnc.gov`, `nccourts.gov`, `uscourts.gov` districts, `sec.gov`, `ecfr.gov`, or `nvca.org`.

Excluded source types and the reason:

- **LegalZoom** — consumer template mill; generic, not jurisdiction-tailored, unsuitable for professional M&A/securities/litigation work.
- **RocketLawyer** — same: consumer-grade generic templates, no jurisdiction-specific drafting or rule tracking.
- **AI template generators** — machine-generated forms with no verified authority, no revision control, and no jurisdictional tailoring.
- **Random SEO PDF mirrors of official forms (pdfFiller and equivalents)** — unofficial copies of court/agency forms that go stale and lose the official revision code; link to the official publisher instead.
- **Other unofficial form aggregators/mirrors (e.g. Justia, formfiles-type sites)** — not the publisher of record; excluded even where they ranked highly in search during research.

This exclusion policy is applied by instruction and by quality bar: consumer template mills and AI template generators are not in this catalog, and no LegalZoom / RocketLawyer / Justia / formfiles / pdfFiller mirror was used as a source for any entry.

## Gather gap-fill exclusions (verified 2026-09-29)

These were checked during the premium-expansion gap-fill and intentionally kept out of git (or refused as form corpora) for the reason stated:

- **Bonterms “M&A NDA” as a separate open form** — No `Bonterms/MA-NDA` (or similarly named) public GitHub repo exists (404). `https://bonterms.com/solutions/bonterms-for-mergers` is a live product/marketing page for running Bonterms One-Way / Mutual NDAs in an M&A workflow on the Bonterms Platform, not a distinct downloadable/open-source M&A NDA form. One-Way NDA is Platform/help-center material (`support.bonterms.com`), not a public Standard Agreement repo like Mutual-NDA. Recorded as excluded rather than inventing a catalog id for a non-existent form.
- **accordproject/template-archive as a form pack** — Live Apache-2.0 repo, but the tree is the Cicero templating engine (`packages/cicero-cli`, `cicero-core`, `generator-cicero-template`), not the form corpus. Catalog points at `accordproject/cicero-template-library` + `templates.accordproject.org` instead (`federal-accordproject-template-library`). Do not submodule the engine under a “templates” path.
- **Ro5s/Startup-Starter-Pack as a submodule** — Public repo, but no LICENSE and the root is a README index of third-party OpenLaw starters, not original form text. Catalog-link only (`federal-startup-starter-pack`).
- **Harvey LAB (`harveyai/harvey-labs`)** — Confirmed again: catalog entry `federal-harvey-lab` exists; ~3GB task corpus stays out of git.
- **Practical Law / Bloomberg Law / Lexis / Westlaw / Matthew Bender** — Hard rule; never in this public repo (Lane F).

