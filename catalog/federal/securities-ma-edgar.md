# Federal — Securities / M&A Deal Precedent on SEC EDGAR

> # ⚠️ MARKET PRECEDENT — USE AS REFERENCE, NOT BLANK TEMPLATES. THESE ARE EXECUTED, DEAL-SPECIFIC AGREEMENTS.
>
> **Label for this entire file: market precedent — use as reference, not blank templates.** These are executed agreements between specific parties, tuned to a specific deal, governing law, and negotiating posture. They are in the public record (no copyright bar to reading and learning from filed documents), but they are not fill-in-the-blank forms and they carry deal-specific concessions. Several (notably Twitter/X) were the subject of litigation that changes how the drafting should be read.

## How to pull deal documents from EDGAR

1. **Full-text search UI (2001–present full text):** [EDGAR Full Text Search](https://www.sec.gov/edgar/search/) — search phrases such as "Agreement and Plan of Merger", filter by form type (8-K, S-4, DEFM14A, SC TO-T), date range, and filer.
2. **Full-text search JSON endpoint (the API behind the UI):** `https://efts.sec.gov/LATEST/search-index?q=%22Agreement+and+Plan+of+Merger%22&forms=8-K&startdt=YYYY-MM-DD&enddt=YYYY-MM-DD` — verified working in this session (returns Elasticsearch-style JSON with `adsh` accession numbers, `ciks`, `form`, `file_type`, `file_description`). Add `&ciks=0000320193` to pin a filer. Requires a descriptive User-Agent header per SEC policy; the automated fetcher used for HTML pages is robots-blocked on `efts.sec.gov`, plain HTTPS requests with a UA work. Documented access rules: [Accessing EDGAR Data](https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data).
3. **Company/browse search and filing indexes:** [SEC Search Filings](https://www.sec.gov/search-filings). Archive URL pattern (verified): `https://www.sec.gov/Archives/edgar/data/<CIK-no-leading-zeros>/<accession-no-dashes>/<accession-with-dashes>-index.htm` for the filing index, and `.../<document-filename>` for the exhibit itself.

Search-workflow tip grounded in the metadata: the EDGAR full-text index returns a `file_type`/`file_description` per document (e.g. "EX-2.1", "EX-5.1", "EX-99.(A)(1)(A)"), so you can isolate exhibit types programmatically instead of opening each filing index.

## Exhibit number conventions (Regulation S-K Item 601 exhibit table)

Confirmed from [17 CFR 229.601 (Item 601) Exhibits](https://www.ecfr.gov/current/title-17/section-229.601):

| Exhibit no. | Item 601 short description | What you find in practice |
|---|---|---|
| 2 (Ex. 2.1) | "Plan of acquisition, reorganization, arrangement, liquidation or succession." | Merger agreements, asset/stock purchase agreements, plans of arrangement |
| 4 (Ex. 4.1) | "Instruments defining the rights of security holders, including indentures." | Indentures, supplemental indentures, notes, warrants, certificates of designation |
| 5 (Ex. 5.1) | "Opinion on legality." | Validity/legality opinions of issuer's counsel in registered offerings |
| 10 (Ex. 10.1) | "Material contracts." | Credit agreements, registration rights agreements, stock purchase agreements, employment/retention agreements, support/voting agreements |
| 99 (Ex. 99.1) | "Additional exhibits." | Press releases, investor decks, offer-to-purchase materials |

## Curated example filings (each URL requested and returning HTTP 200)

| Document/Form | Type | Publisher/Authority | Source Page URL | Document URL | Access | Quality Notes |
|---|---|---|---|---|---|---|
| Activision Blizzard, Inc. Form 8-K filed 2022-01-19 — Microsoft acquisition | Ex. 2.1 Agreement and Plan of Merger (public-company cash merger, one-step) | Filer: Activision Blizzard (CIK 0000718877), filed with SEC EDGAR | [EDGAR filing index 0001104659-22-005154](https://www.sec.gov/Archives/edgar/data/718877/000110465922005154/0001104659-22-005154-index.htm) | [EX-2.1](https://www.sec.gov/Archives/edgar/data/718877/000110465922005154/tm223212d3_ex2-1.htm) | Free (EDGAR) | Market precedent — use as reference, not a blank template. Mega-cap strategic cash merger; useful for regulatory-efforts/"hell-or-high-water" covenants, ticking fee/outside date architecture. Exhibit type "EX-2.1" per EDGAR full-text index metadata |
| Twitter, Inc. Form 8-K filed 2022-04-26 — Musk/X Holdings take-private | Ex. 2.1 Agreement and Plan of Merger; same filing also carries Ex. 4.2 | Filer: Twitter, Inc. (CIK 0001418091), SEC EDGAR | [EDGAR filing index 0001193125-22-120461](https://www.sec.gov/Archives/edgar/data/1418091/000119312522120461/0001193125-22-120461-index.htm) | [EX-2.1](https://www.sec.gov/Archives/edgar/data/1418091/000119312522120461/d310843dex21.htm) · [EX-4.2](https://www.sec.gov/Archives/edgar/data/1418091/000119312522120461/d310843dex42.htm) | Free (EDGAR) | Market precedent — reference only. The canonical modern LBO/take-private with specific-performance and equity-financing structure; heavily litigated, so read alongside the Delaware record |
| Twitter, Inc. Schedule 13D filed 2022-04-05 (Elon Musk) | SC 13D beneficial ownership statement | Filed with SEC EDGAR (subject: Twitter, Inc., CIK 0001418091) | [EDGAR filing index 0001104659-22-042863](https://www.sec.gov/Archives/edgar/data/1418091/000110465922042863/0001104659-22-042863-index.htm) | [SC 13D document](https://www.sec.gov/Archives/edgar/data/1418091/000110465922042863/tm2211757d1_sc13d.htm) | Free (EDGAR) | Market precedent — reference only. Best-known recent 13D; useful model for Item 4 "Purpose of Transaction" drafting and late-filing risk analysis |
| Whole Foods Market, Inc. Form 8-K filed 2017-06-16 — Amazon acquisition | Ex. 2.1 Agreement and Plan of Merger (also filed as DEFA14A soliciting material) | Filer: Whole Foods Market (CIK 0000865436), SEC EDGAR | [EDGAR filing index 0001047469-17-004058](https://www.sec.gov/Archives/edgar/data/865436/000104746917004058/0001047469-17-004058-index.htm) | [EX-2.1](https://www.sec.gov/Archives/edgar/data/865436/000104746917004058/a2232461zex-2_1.htm) · related [Ex. 10.1 filed 2017-07-05](https://www.sec.gov/Archives/edgar/data/865436/000110465917043498/a17-16920_1ex10d1.htm) ([index](https://www.sec.gov/Archives/edgar/data/865436/000110465917043498/0001104659-17-043498-index.htm)) · [DEFM14A merger proxy 2017-07-21](https://www.sec.gov/Archives/edgar/data/865436/000157104917006849/t1702075-defm14a.htm) | Free (EDGAR) | Market precedent — reference only. Clean single-step cash merger plus a full merger-proxy (Schedule 14A) precedent chain: PREM14A → DEFM14A → DEFA14A |
| Snap Inc. Form S-1/A filed 2017-02-16 (IPO) | Ex. 5.1 opinion on legality; Ex. 1.1 underwriting agreement; Ex. 10.x material contracts in the original S-1 | Filer: Snap Inc. (CIK 0001564408), SEC EDGAR | [EDGAR filing index 0001193125-17-045870](https://www.sec.gov/Archives/edgar/data/1564408/000119312517045870/0001193125-17-045870-index.htm) | [EX-5.1 legal opinion](https://www.sec.gov/Archives/edgar/data/1564408/000119312517045870/d270216dex51.htm) · [EX-1.1 underwriting agreement](https://www.sec.gov/Archives/edgar/data/1564408/000119312517045870/d270216dex11.htm) · original [S-1 (2017-02-02)](https://www.sec.gov/Archives/edgar/data/1564408/000119312517029199/d270216ds1.htm) ([index](https://www.sec.gov/Archives/edgar/data/1564408/000119312517029199/0001193125-17-029199-index.htm)) | Free (EDGAR) | Market precedent — reference only. Benchmark tech IPO (non-voting Class A structure); good Ex. 5.1 opinion form and Ex. 10 series for equity plans/investor agreements |
| Apple Inc. Form 8-K filed 2013-05-03 (inaugural bond offering) | Ex. 4.1 indenture; Ex. 5.1 opinion; Ex. 1.1 underwriting agreement | Filer: Apple Inc. (CIK 0000320193), SEC EDGAR | [EDGAR filing index 0001193125-13-199324](https://www.sec.gov/Archives/edgar/data/320193/000119312513199324/0001193125-13-199324-index.htm) | [EX-4.1 indenture](https://www.sec.gov/Archives/edgar/data/320193/000119312513199324/d529124dex41.htm) · [EX-5.1](https://www.sec.gov/Archives/edgar/data/320193/000119312513199324/d529124dex51.htm) · [EX-1.1](https://www.sec.gov/Archives/edgar/data/320193/000119312513199324/d529124dex11.htm) | Free (EDGAR) | Market precedent — reference only. Investment-grade base indenture + covenant package; classic Ex. 4.1 / Ex. 5.1 pairing for a shelf takedown |
| Horizon Global Corp. Schedule TO-T filed 2023-01-10 (third-party cash tender offer) | SC TO-T with Ex. 99(a)(1)(A) Offer to Purchase and related offer documents; later SC TO-T/A amendments | Filed with SEC EDGAR (subject: Horizon Global Corp., CIK 0001637655) | [EDGAR filing index 0001193125-23-004962](https://www.sec.gov/Archives/edgar/data/1637655/000119312523004962/0001193125-23-004962-index.htm) | [SC TO-T](https://www.sec.gov/Archives/edgar/data/1637655/000119312523004962/d433995dsctot.htm) · [EX-99.(A)(1)(A) Offer to Purchase](https://www.sec.gov/Archives/edgar/data/1637655/000119312523004962/d433995dex99a1a.htm) · [SC TO-T/A 2023-02-07](https://www.sec.gov/Archives/edgar/data/1637655/000119312523027109/d449122dsctota.htm) | Free (EDGAR) | Market precedent — reference only. Shows the Reg M-A exhibit lettering convention for tender offers ((a)(1)(A)-(a)(5), (b), (d)) rather than Item 601 numbering |


## 2026-09-29 — Form-of blanks (not the IPO registration-rights set)

Clean **Form of** exhibits only. Execution-version premier documents (Charter 2016 first-lien intercreditor; T-Mobile USA 2020 credit agreement; Dell 2016 base indenture) were not mirrored. Microcap and SPAC "form of" escrows, guaranties, and intercreditors were rejected. No premier Form-of intercreditor with clean blanks was on EDGAR. LSTA intercreditor forms remain member-gated; see [credit-financing.md](credit-financing.md).

| Document | Type | Document URL | Drive |
|---|---|---|---|
| Guggenheim Credit Income Fund 2019 Form of Escrow Agreement | Offering escrow (UMB); blank date | [EX-99.(K)(1)](https://www.sec.gov/Archives/edgar/data/1618696/000161869618000055/ex99k12019escrow.htm) | `1DWqKY-aarauu9ZTdUGnKcWgx3hACZWwV` |
| JPM Form of Paying Agent Agreement for Notes | Paying / registrar / authenticating agent | [EX-4.R.2](https://www.sec.gov/Archives/edgar/data/19617/000095010316012353/dp64654_ex04r2.htm) | `1a7rUC2jsN93kll_tRgN12qWyhEFERpI5` |
| JPM Form of Paying Agent Agreement for Warrants | Warrant paying agent | [EX-4.R.3](https://www.sec.gov/Archives/edgar/data/19617/000095010316012353/dp64654_ex04r3.htm) | `13AkbKCgILBGaWVUh8zHYYPqTmJAjWbzK` |
| B&W Enterprises Form of Credit Agreement | Syndicated revolver form (BofA admin agent) | [EX-10.19](https://www.sec.gov/Archives/edgar/data/1630805/000119312515195380/d888282dex1019.htm) | `1c2-KjbIT0Emt_Z1kSIls6hgqDv0aH7Zw` |
| CBS Operations Form of Guarantee | Indenture endorsement guarantee | [EX-4.4](https://www.sec.gov/Archives/edgar/data/813828/000119312517332895/d456645dex44.htm) | `1A93kyiQddJ0Cak6-MjR8F--BVQi0_34Y` |
| Denali/Dell Form of A&R Registration Rights Agreement | Sponsor shelf / demand RRA; blank date. Not the IPO IRA set | [EX-10.2](https://www.sec.gov/Archives/edgar/data/1571996/000119312516586396/d73946dex102.htm) | `1pojUUV_nW2DtkVCBEZ3G8BTd932m73uq` |
| Alphabet Form of Indemnification Agreement | Public-company D&O form; not NVCA | [EX-10.4](https://www.sec.gov/Archives/edgar/data/1652044/000119312515336577/d82837dex104.htm) | `1WQaYtWGsoa4nW5f7MOfLlDN_VoGGtPag` |

## 2026-09-29 evening — wave 2 Form-of (spins + JPM note/warrant)

Premier **Form of** spin and structured-product exhibits. Mega-cap Apple/MSFT/AMZN/META/Disney/Boeing EX-4 debt docs were execution officers' certificates or supplemental indentures and were not mirrored. No premier blank-quality Form of Support, Voting (non-NVCA), Intercreditor, or M&A escrow was located; SPAC/microcap hits rejected. LSTA intercreditor remains member-gated.

| Document | Type | Document URL | Drive |
|---|---|---|---|
| J&J/Kenvue Form of Tax Matters Agreement | Spin TMA | [EX-10.2](https://www.sec.gov/Archives/edgar/data/1944048/000162828023012570/exhibit102-sx1a4.htm) | `10e_joydW_ybSWx47S7DtOTTbZFFT9-LX` |
| J&J/Kenvue Form of Employee Matters Agreement | Spin EMA | [EX-10.3](https://www.sec.gov/Archives/edgar/data/1944048/000162828023002224/exhibit103-sx1a.htm) | `10Ngh-S9nTnX5_T2I0fS6sZ289Qtvzbpu` |
| Lilly/Elanco Form of Tax Matters Agreement | Spin TMA | [EX-10.3](https://www.sec.gov/Archives/edgar/data/1739104/000104746918005982/a2236595zex-10_3.htm) | `1iH7RHB6rolDx3lOZ1edStRYgWSOKosph` |
| Lilly/Elanco Form of IP and Technology License | Spin IP license | [EX-10.8](https://www.sec.gov/Archives/edgar/data/1739104/000104746918005844/a2236501zex-10_8.htm) | `11BEm0qD-AQT1F9ptvggPB8FbJ9hZf7SO` |
| GE/GEHC Form of Tax Matters Agreement | Spin TMA | [EX-10.2](https://www.sec.gov/Archives/edgar/data/1932393/000119312522260650/d379971dex102.htm) | `1hReOAY2lifwnG1rV2KnBl_gTgfaNjKI8` |
| GE/GEHC Form of Employee Matters Agreement | Spin EMA | [EX-10.3](https://www.sec.gov/Archives/edgar/data/1932393/000119312522279103/d379971dex103.htm) | `1bb2WNXC7fqqxMqxpUWbcgve1a5EfnprK` |
| GE/GEHC Form of Trademark License | Spin IP | [EX-10.4](https://www.sec.gov/Archives/edgar/data/1932393/000119312522260650/d379971dex104.htm) | `1RWMS0_J208FUVaUD7YWqkEyOnczgOy2e` |
| GE/GEHC Form of Stockholder and Registration Rights | Spin SHA/RRA | [EX-10.6](https://www.sec.gov/Archives/edgar/data/1932393/000119312522260650/d379971dex106.htm) | `1vmWrNk5My4Ot88UQqcHT3tIjaBiZ6KRZ` |
| GE/GEHC Form of Transition Services Agreement | Spin TSA | [EX-10.1](https://www.sec.gov/Archives/edgar/data/1932393/000119312522260650/d379971dex101.htm) | `1DdPsyLxqD6Leqlc74YsZzgFvd3Qd8Q2t` |
| Ashland/Valvoline Form of Tax Matters Agreement | Spin TMA | [EX-10.4](https://www.sec.gov/Archives/edgar/data/1674910/000119312516664822/d176840dex104.htm) | `1i_v9_ja6qQSvZUsvwBNUr0Q6TY8Kke2Q` |
| IAC/Match Form of Employee Matters Agreement | Spin EMA | [EX-10.2](https://www.sec.gov/Archives/edgar/data/1575189/000104746915008217/a2226380zex-10_2.htm) | `1J0qpHYEf2z7Bh0YY8_GFVzNq-mNf-gP_` |
| Lockheed/Leidos Form of IP Matters Agreement | Spin IP | [EX-2.3](https://www.sec.gov/Archives/edgar/data/1336920/000119312516633459/d162784dex23.htm) | `1dUs0CdbGhjLWloC9SMwHV9x9NNgpPpKZ` |
| JPM Form of Note (MTN Series A) | Form of Note | [EX-4.B.5](https://www.sec.gov/Archives/edgar/data/19617/000095010316011338/dp63627_ex4b5.htm) | `1FvxFgh9p5bTAjEinQ0CMYbSPQangMEiE` |
| JPM Non-U.S. Distribution Form of Note | Form of Note | [EX-4.B.6](https://www.sec.gov/Archives/edgar/data/19617/000095010316011338/dp63627_ex4b6.htm) | `1aEH66I2cTEXxjJ8GVNoPALbSw5ceSsc9` |
| JPM Form of Warrant | Form of Warrant | [EX-4.M.1](https://www.sec.gov/Archives/edgar/data/19617/000095010316011338/dp63627_ex4m1.htm) | `1GTLMB4WuoX2UmnRpi2jxDNo1SPVrMm1l` |
| JPM Form of Warrant Indenture | Form of Indenture | [EX-4.A.8](https://www.sec.gov/Archives/edgar/data/19617/000095010316011338/dp63627_ex4a8.htm) | `1QiiKxBVj7RjV7F6tUK5xzrofpLgoICjM` |

## 2026-09-29 late — wave 3 Form-of (Separation / Supply / new-issuer spin suite)

Premier **Form of** / blank-dated spin exhibits filling Separation/Distribution, Master Separation, new-issuer EMA/TMA, TSA beyond GEHC/J&J, Supply, and IP gaps. Execution Separations (PayPal/Dow/Keysight/GE Vernova) and SPAC/microcap Support/Convertible Indenture hits rejected. No premier blank-quality Form of Support/Voting/Proxy or Convertible Notes Indenture located.

| Document | Type | Document URL | Drive |
|---|---|---|---|
| Labcorp/Fortrea Form of Separation and Distribution | Spin Separation | [exhibit21-10x12ba.htm](https://www.sec.gov/Archives/edgar/data/1965040/000162828023020696/exhibit21-10x12ba.htm) | `1dkcKVz2gWsqW-aC70UbEy_utMR9eyRQZ` |
| Labcorp/Fortrea Form of Tax Matters Agreement | Spin TMA | [exhibit101-10x12ba.htm](https://www.sec.gov/Archives/edgar/data/1965040/000162828023020696/exhibit101-10x12ba.htm) | `1HUkG0I6Iqpk7f9wqdO2Yaz4KyZXdMBPk` |
| Labcorp/Fortrea Form of Employee Matters Agreement | Spin EMA | [exhibit102-10x12ba.htm](https://www.sec.gov/Archives/edgar/data/1965040/000162828023020696/exhibit102-10x12ba.htm) | `16uZuTlb11tvankZxojgscg8q3gFdByea` |
| Labcorp/Fortrea Form of Transition Services Agreement | Spin TSA | [exhibit103-10x12ba.htm](https://www.sec.gov/Archives/edgar/data/1965040/000162828023020696/exhibit103-10x12ba.htm) | `1TeKLMQ9nzKe1THhPPBmxq8B60u31LBXd` |
| 3M/Solventum Form of Separation and Distribution | Spin Separation | [exhibit21-form10.htm](https://www.sec.gov/Archives/edgar/data/1964738/000162828024005591/exhibit21-form10.htm) | `1gdNfAsX0Btr4l5cCZNc-bRa3cNpZvRUZ` |
| 3M/Solventum Form of Transition Services Agreement | Spin TSA | [exhibit101-form10.htm](https://www.sec.gov/Archives/edgar/data/1964738/000162828024005591/exhibit101-form10.htm) | `1HMZgbHWXJBoRmEbHt6b8J9epZ82Hktic` |
| 3M/Solventum Form of Tax Matters Agreement | Spin TMA | [exhibit102-form10.htm](https://www.sec.gov/Archives/edgar/data/1964738/000162828024005591/exhibit102-form10.htm) | `104F7S7Unomrll-T7kr-eqidhADu512HK` |
| 3M/Solventum Form of Employee Matters Agreement | Spin EMA | [exhibit103-form10.htm](https://www.sec.gov/Archives/edgar/data/1964738/000162828024005591/exhibit103-form10.htm) | `1ANpLpXl7YPqmAHFShEiUuGpI5aBaJVAC` |
| 3M/Solventum Form of IP Cross License | Spin IP | [exhibit108-form10.htm](https://www.sec.gov/Archives/edgar/data/1964738/000162828024005591/exhibit108-form10.htm) | `1M__QttdZKUWRS34ZhJg3reUNZWN65U3e` |
| 3M/Solventum Form of Master Supply Agreement | Spin Supply | [exhibit1011-form10.htm](https://www.sec.gov/Archives/edgar/data/1964738/000162828024005591/exhibit1011-form10.htm) | `156j7pHcsZ_7i4uMpRmznEErS7m3PjKb0` |
| Fortive/Ralliant Form of Separation and Distribution | Spin Separation | [tm2429554d6_ex2-1.htm](https://www.sec.gov/Archives/edgar/data/2041385/000110465925044355/tm2429554d6_ex2-1.htm) | `1OGJ_vRMTWqRMEn3If4VsFqFX5FDJ8DP6` |
| Fortive/Ralliant Form of Transition Services Agreement | Spin TSA | [tm2429554d6_ex10-1.htm](https://www.sec.gov/Archives/edgar/data/2041385/000110465925044355/tm2429554d6_ex10-1.htm) | `1yYguSkcIbhAmA8Y7Np5JCcRnxVKic66z` |
| Fortive/Ralliant Form of Tax Matters Agreement | Spin TMA | [tm2429554d6_ex10-2.htm](https://www.sec.gov/Archives/edgar/data/2041385/000110465925044355/tm2429554d6_ex10-2.htm) | `1hFIGEsoTC3N76MO-iPMnzXL56Lnf9D_I` |
| Fortive/Ralliant Form of Employee Matters Agreement | Spin EMA | [tm2429554d6_ex10-3.htm](https://www.sec.gov/Archives/edgar/data/2041385/000110465925044355/tm2429554d6_ex10-3.htm) | `1rW8TqBDbkCtNGR_hCgRAoamUYkeAc06m` |
| Honeywell/Resideo Form of Separation and Distribution | Spin Separation | [d601987dex21.htm](https://www.sec.gov/Archives/edgar/data/1740332/000119312518290883/d601987dex21.htm) | `1GhGAm7sxVuYKvWcBuEWuD2Try608q4MJ` |
| Honeywell/Resideo Form of Tax Matters Agreement | Spin TMA | [d601987dex23.htm](https://www.sec.gov/Archives/edgar/data/1740332/000119312518290883/d601987dex23.htm) | `1vWvIO3bUXI6OJmX_u4_I5CagHaBQD5aH` |
| Kellogg/WK Kellogg Form of Separation and Distribution | Spin Separation | [d456637dex21.htm](https://www.sec.gov/Archives/edgar/data/1959348/000119312523192363/d456637dex21.htm) | `1A8psUjgxdoqTVOZzshcUb-1Obw9NXHv9` |
| Kellogg/WK Kellogg Form of Supply Agreement | Spin Supply | [d456637dex102.htm](https://www.sec.gov/Archives/edgar/data/1959348/000119312523192363/d456637dex102.htm) | `1SROXW4GWaHZaHjYkaNrZby4zFkZyMTOE` |
| Kellogg/WK Kellogg Form of Tax Matters Agreement | Spin TMA | [d456637dex105.htm](https://www.sec.gov/Archives/edgar/data/1959348/000119312523192363/d456637dex105.htm) | `1fRApsqKzENw3rge_elN7gAs7M37rJdWt` |
| Kellogg/WK Kellogg Form of Transition Services Agreement | Spin TSA | [d456637dex106.htm](https://www.sec.gov/Archives/edgar/data/1959348/000119312523192363/d456637dex106.htm) | `1k6qB91_cBjgSbuLIy8dNNdYoz8oQS1H_` |
| Danaher/Envista Form of Separation Agreement | Spin Separation | [nvst-s1xex101.htm](https://www.sec.gov/Archives/edgar/data/1757073/000175707319000010/nvst-s1xex101.htm) | `18G-RHpRmORKLm3qimH-VeKhLk61hKl9Y` |
| Danaher/Envista Form of Transition Services Agreement | Spin TSA | [nvst-s1xex102.htm](https://www.sec.gov/Archives/edgar/data/1757073/000175707319000010/nvst-s1xex102.htm) | `1m3ovhEyWGH7sW8C_riGJuqdtlVERdtRv` |
| Danaher/Envista Form of Tax Matters Agreement | Spin TMA | [nvst-s1xex103.htm](https://www.sec.gov/Archives/edgar/data/1757073/000175707319000010/nvst-s1xex103.htm) | `1maQICQaUgiBX8QPnaPc3Ij27k3eHs3VE` |
| Danaher/Envista Form of IP Matters Agreement | Spin IP | [nvst-s1xex105.htm](https://www.sec.gov/Archives/edgar/data/1757073/000175707319000010/nvst-s1xex105.htm) | `1NUN2FGOLmiNRvCQNfuYlfzDxcMIcXMk9` |
| Lilly/Elanco Form of Master Separation Agreement | Master Separation | [a2236501zex-10_1.htm](https://www.sec.gov/Archives/edgar/data/1739104/000104746918005844/a2236501zex-10_1.htm) | `1PGxsQbGNDYzV120XH13TX0lRq-HdyN8Z` |
| Fortune Brands/MasterBrand Form of Separation and Distribution | Spin Separation | [d307794dex21.htm](https://www.sec.gov/Archives/edgar/data/1941365/000119312522290185/d307794dex21.htm) | `1ibc5ga4YWdkvfQcmtiNU9B847bUh6287` |
| Fortune Brands/MasterBrand Form of Employee Matters Agreement | Spin EMA | [d307794dex102.htm](https://www.sec.gov/Archives/edgar/data/1941365/000119312522290185/d307794dex102.htm) | `1JQokRL6PpU096BTy9hTv8IgIzObxgQSb` |
| Conagra/Lamb Weston Form of Separation and Distribution | Spin Separation | [d205931dex21.htm](https://www.sec.gov/Archives/edgar/data/1679273/000119312516693702/d205931dex21.htm) | `1v_LgZMmAAqnoX4g2-PZTlOCGIwxCyrwB` |
| Conagra/Lamb Weston Form of Transition Services Agreement | Spin TSA | [d205931dex103.htm](https://www.sec.gov/Archives/edgar/data/1679273/000119312516693702/d205931dex103.htm) | `1moNvZU2J6Pd1oToms3t4Z_MRIm1_jZv6` |
| B&W Form of Master Separation Agreement | Master Separation | [d888282dex21.htm](https://www.sec.gov/Archives/edgar/data/1630805/000119312515195380/d888282dex21.htm) | `19aEbEHp7xWPGddl6W4lcsVUZCUMHGTFO` |
