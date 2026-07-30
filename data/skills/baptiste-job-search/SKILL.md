---
name: baptiste-job-search
description: Baptiste's complete job search system — tracked sites, search criteria, scouting workflow, application pipeline management, and the generic web extraction technique that powers it.
category: research
---

# Baptiste Job Search System

## Purpose
Centralize and automate Baptiste's job search for finance roles in Paris, London, and New York. This skill tracks which sites to monitor, what Baptiste is looking for, provides a structured workflow for scouting AND applying — and includes the generic web-search → extract → format pipeline that Baptiste's config is built on.

**Live scan results**: See `references/scan-2026-06-30.md` for the most recent scan. Previous scans: `scan-2026-06-29.md`, `scan-2026-06-26.md`, `scan-2026-06-25.md`, `scan-2026-06-24.md`, `scan-2026-06-05.md`, `scan-2026-06-04.md`, `scan-2026-06-03.md`. For scan execution patterns, see `references/scan-workflow-guide.md`. Subsequent scans should create new dated files.

---

## Baptiste's Profile (DO NOT re-ask — use these facts)
- **Background**: iVY league business school
- **Target roles**: Private Equity, Hedge Fund, Investment Banking, M&A
- **Target locations**: Paris, London, New York (in that order of preference)
- **Start date**: January 2027 (internship / stage)
- **Language**: French by default; English OK for search/content
- **Preferences**: concise & structured, no corporate filler

### Search Criteria Priorities
1. **PE / Private Equity** roles (top preference)
2. **M&A / Investment Banking** roles
3. **Hedge Fund** roles
4. Salary transparency is a plus
5. Mid-size to large firms preferred over boutiques (for structured training)
6. Open to off-cycle internships if relevant

---

## Monitored Sites

### Tier 1 — High priority (check every 1-2 days)
| Site | URL | Access | Notes |
|------|-----|--------|-------|
| **LinkedIn** | linkedin.com/jobs | Public (API-limited) | Best for PE/HF/IB roles, filter by Paris + London |
| **eFinancialCareers** | efinancialcareers.fr / .com | Public | Finance专属, strong for Paris/London |
| **Glassdoor** | glassdoor.fr | Public | Salary data available |
| **Indeed** | indeed.fr / .com | Public | Broad coverage |

### Tier 2 — Mid priority (check every 3-7 days)
| Site | URL | Access | Notes |
|------|-----|--------|-------|
| **Wall Street Oasis (Talent Oasis)** | wallstreetoasis.com/talent | Login required, email notify | Niche finance roles not on LinkedIn. Baptiste should register and set email alerts. Has a forum with off-cycle/IB/PE discussions. |
| **Wellfound (ex-AngelList)** | wellfound.com | Public | Startup/VC roles, for emerging managers |
| **Careers de Lazard, Rothschild, etc.** | Various | Public | Firm-specific careers pages |
| **BNP Paribas / Société Générale careers** | group.bnpparibas/en/careers societegenerale.com/en/careers | Public | Top French banks, structured programs |
| **KKR** | kkr.com/careers | Public | Top-tier PE, Paris internships 2026-2027 |
| **Astorg** | astorg.com/careers | Public | European mid-large cap PE, Paris |
| **Blackstone** | blackstone.com/careers | Public | Largest PE firm, off-cycle + Summer Analyst (Paris, London, NYC). Has PE, Infrastructure Partners, Strategic Partners (Secondaries), Credit & Insurance tracks. |
| **Jefferies** | jefferies.tal.net | Public | IB off-cycle, London + Paris |
| **The Trackr EU** | app.the-trackr.com/eu-finance/off-cycle-internships | Public | Tracker live des off-cycles EU finance (Rothschild PE, Astorg PE, etc.). **⚠️ Defaults to "Summer Internships" tab — must click "Off-Cycle Internships" to see the right data.** |
| **The Trackr France** | app.the-trackr.com/france-finance/off-cycle-internships | Public | Tracker off-cycle France-only. Meilleure couverture pour Paris que le tracker EU. |
| **The Trackr US** | app.the-trackr.com/us-finance-2027/summer-internships | Public | Tracker des Summer Analyst US (BB, boutiques, PE). **URL changée : ancien `us-finance/` redirige maintenant vers `us-finance-2027/summer-internships`. Toujours checker pour NYC. |
| **The Trackr UK** | app.the-trackr.com/uk-finance/off-cycle-internships | Public | Tracker off-cycle UK/London. **⚠️ Defaults to "Summer Internships" tab — must click "Off-Cycle Internships" to see the right data. Séparer du tracker EU.** |
| **Jobortunity** | jobortunity.ai/en/trackers/eu-finance-off-cycle | Public | Tracker agrégé, 436+ offres live, couvre PE/IB/M&A EU |
| **Goldman Sachs Careers** | higher.gs.com/roles | Public | Portail canonical pour offres GS. Rechercher "2027 EMEA" + ville. |
| **Trabajo.org** | fr.trabajo.org | Public | Agrégateur d'offres francophone, bonne couverture Paris (Evercore, Nomura, etc.) |
| **Rothschild Five Arrows** | rothschildandco.com/en/careers/students-and-graduates/opportunities/ | Public | PE Secondaires (FASO), Co-investment, Growth Partners, Infra Debt, IR — souvent listé en janvier/mars et juillet/septembre. |
| **Insight Partners** | insightpartners.com/Summer-Analyst-Program.html | Public | Growth equity / VC NYC, applications ouvertes tôt (sept 2025 pour 2027). |
| **D.E. Shaw (Cove)** | deshaw.com/careers/ | Public | Hedge fund / multi-strat, offre "Cove Private Equity Intern" à NYC. |
| **INDEFI GROUP** | indefi.com/careers/ | Public | Strategy consulting / PE advisory, Paris/Lyon/Madrid. Stages "Strategy Consultant Internship - Private Equity". |
| **Citadel** | citadel.com/careers/details/ | Public | Hedge fund — Equities Associate Intern (NYC + London). Summer applications open early, rolling basis. |
| **Point72** | careers.point72.com | Public | Hedge fund — Academy Investment Analyst Program (10 months, buy-side training). ONE application only globally. |
| **GP Bullhound** | gpbullhound.com/jobs/ | Public | Tech-focused investment bank, London + Paris. Off-cycle & summer internships. |

### Tier 3 — Reference only (check biweekly)
| Site | URL | Access | Notes |
|------|-----|--------|-------|
| **Welcome to the Jungle** | welcometothejungle.com | Public | Good for company culture info |
| **Cadremploi** | cadremploi.fr | Public | French generalist |
| **Pole Emploi / France Travail** | francetravail.fr | Public | Official, sparse for finance |

---

## Search Queries

### For LinkedIn
```
Private Equity Analyst Paris | Analyste Private Equity Paris
Investment Banking Analyst Paris Londres
M&A Analyst Paris January 2026
Off-cycle internship finance Paris
```

### For eFinancialCareers
```
Analyst - Private Equity - Paris
Analyst - M&A - London
Internship - Investment Banking - Paris 2027
```

### For Indeed
```
"private equity" "analyst" Paris
"investment banking" "intern" London 2026
"stage M&A" Paris janvier 2027
```

### Generic web search (for special/rare roles)
```
"private equity analyst" Paris London 2026 2027 internship
"off cycle internship" investment banking Paris 2026
"analyste private equity" stage Paris 2027
```

### For Rothschild & Co specifically
```
Rothschild "Five Arrows" OR "FASO" internship Paris 2027
Rothschild "private equity secondaire" OR "co-investissement" Paris 2027
Rothschild "investor relations" "Five Arrows" Paris
```

### For growth equity / VC (NYC-focused)
```
Lead Edge Capital 2027 summer analyst New York
D.E. Shaw Cove private equity intern 2027
Insight Partners summer analyst 2027 New York
```

---

## Scouting Workflow

### When asked "check for new offers" or "scan job sites":
1. **Read previous scan files** (`references/scan-*.md`) to know what's already found.
2. **Scan all three cities in parallel** if possible — use `delegate_task` with 3 workers (one per city) to run faster.
3. **Scan all three cities equally** — Paris, London, NYC. Do not let EU-focused trackers dominate the results.
4. **Always check Tier 1 first** — LinkedIn + eFinancialCareers are the highest yield.
5. Use `web_search` with queries from above (limit 10-15 results). Run separate queries per city.
6. Use web_extract on the Trackr pages for each region: EU, UK, France, and US (fallback to web_search if Trackr US returns 500). **⚠️ IMPORTANT**: All Trackr pages default to "Summer Internships" tab. You MUST click "Off-Cycle Internships" button first to load the correct data. If web_extract fails due to "Payment Required" (Firecrawl credit exhaustion), immediately fall back to browser-based extraction using browser_navigate + browser_console with JavaScript to extract and filter relevant offers (see references/trackr-browser-extraction.md for the base pattern). After extracting the table rows, filter for roles containing keywords (private equity, PE, M&A, investment banking, IB, hedge fund, HF) and/or containing "2027" in the programme name, then sort by opening date (most recent first) and take the top 4 per region. For EU tracker, also check the France-specific tracker (app.the-trackr.com/france-finance/off-cycle-internships) for better Paris coverage.
7. For any promising URL, use `web_extract` to get details. **For Goldman Sachs**: always check `higher.gs.com/careers/students/programs-and-internships/emea/off-cycle-internships` and check ALL open windows per city — GS posts multiple distinct roles with different start dates in the same recruiting year. **⚠️ Before reporting any GS role**, check `/opt/data/career/applications.md` to verify whether Baptiste has already used any of his max 4 annual GS applications.
7. **Deduplicate** by company + title across sites AND against previous scans. Only include an offer if it's NEW or has new info (deadline change, status update).
8. **Format output: exactly 4 offers per city (12 total), grouped by city with flag emoji.**
   ## �🇷 PARIS
   1. **Title** — Company
      - Details: duration, start date, deadline if applicable
      - Source: URL
   ## �🇧 LONDON
   (same format)
   ## �🇸 NEW YORK
   (same format)
   If fewer than 4 offers exist for a city, state explicitly: "Seulement X offres disponibles pour [ville]."
9. **Add "Nouveautés" comparison table** at the end of each scan: list which offers are new vs the previous scan (%, 🆕 for new, 🔄 for confirmed returning). This is the most actionable section for Baptiste — it lets him focus only on fresh leads.

### When to flag something to Baptiste:
- Role matches PE/HF/M&A in Paris, London, or New York with a Jan 2027 start
- Off-cycle internship at a BB or known PE firm
- Salary data above market
- "Easy apply" or fast application processes
- Roles with deadlines approaching (mark with ⚠️)

### When NOT to flag:
- Internships starting before July 2026 (probably too early for Baptiste)
- Graduate programs requiring 0-2 years experience that started recruiting in fall 2025
- Sales/trading or non-target roles
- KKR London Summer Analyst (typically closes by spring — verify status before reporting)

---

## Application Tracker

When Baptiste tells me he applied to something, log it to `/opt/data/career/applications.md`.

Format:
```markdown
## YYYY-MM-DD
- **Role**: [title]
- **Company**: [name]
- **Location**: [city]
- **Site**: [source URL]
- **Status**: Applied / Interview / Rejected / Ghosted
- **Notes**: [anything relevant]
```

---

## Wall Street Oasis Specific Guidance

WSO is a forum, not a traditional job board. The best value:
1. **Forum > Job Search section**: Users share recruiting timelines, interview prep, and sometimes unadvertised openings.
2. **Talent Oasis** (wallstreetoasis.com/talent/employees): Exclusive job board but requires login.
3. **Networking**: Baptiste should create an account and engage — many finance pros recruit through WSO connections.

**Action for Baptiste**: Register at wallstreetoasis.com and set up job email alerts if possible.

---

## Pitfalls
- LinkedIn heavily rate-limits scraping; prefer web_search with `site:linkedin.com`
- eFinancialCareers loads listings dynamically via JS — use web_search, not direct scraping
- WSO job board requires login; don't waste time trying to scrape it
- French dates: "janvier 2027" = January 2027; internships often listed as "Stage de fin d'études"
- Don't re-ask Baptiste for his profile or preferences — they're above
- **EU bias trap**: The Trackr EU finance tracker and eFinancialCareers are Paris/London-heavy. Always also check the Trackr US finance tracker (app.the-trackr.com/us-finance/) and run explicit NYC queries to get balanced coverage. A scan that returns only Paris offers is a methodology failure, not a market reality.
- **US recruiting timeline**: US firms recruit 12-18 months ahead. Summer 2027 analyst programs may already be closed or closing soon. Always note the deadline status.
- **Goldman Sachs application cap**: max 4 applications per recruiting year across ALL locations and divisions (EMEA + US + Asia). Additional applications are auto-withdrawn. Always check if Baptiste has already applied to GS before submitting. The canonical job detail URL is `higher.gs.com/roles/{id}` (not the careers portal). GS posts multiple off-cycle windows per cohort year — e.g., "Jan–Mars 2027" (higher.gs.com/roles/170844) and "Avril–Juin 2027" (higher.gs.com/roles/170843) are distinct roles. Always browse the off-cycle page to find all open windows. **⚠️ Verifying GS deadlines**: Third-party aggregators (Simplify, Trackr, LinkedIn) frequently confuse the recruiting year. Always verify GS application open dates and deadlines directly on `goldmansachs.com/careers/students/programs-and-internships/` — e.g., 2027 Summer Analyst applications open August 15, 2026 (NOT Jan 1 as some aggregators claim).
- **Trackr UK tracker** (app.the-trackr.com/uk-finance/off-cycle-internships) is separate from the EU tracker and covers London-specific roles. Always check both.
- **Duplicate prevention**: Before finalizing a scan, cross-reference company + title against `references/scan-*.md` files. If an offer appears in the last 2 scans, only re-include it if there's new information (e.g., deadline changed, status updated).
- **Lincoln International MBA-only**: Lincoln's Q1 M&A internships in Berlin are restricted to Master's students. Note this in the output if included.
- **Trabajo.org coverage**: This French job aggregator often lists roles from Evercore, Nomura, and other boutiques before they appear on eFinancialCareers. Always check `fr.trabajo.org` with queries like "off-cycle internship Paris" for the latest postings.
- **Trackr US URL pattern**: The Trackr US page uses a year-specific path format (e.g., `app.the-trackr.com/us-finance-2027/summer-internships` for 2027 programs). Always verify the current year's path before scanning. If the direct page fails, use `web_search` with `site:app.the-trackr.com/us-finance-*` as a workaround.
- **Trackr tab default trap**: All Trackr trackers (EU, UK, France) default to the "Summer Internships" tab. You MUST click "Off-Cycle Internships" to see off-cycle roles. Always click the correct tab before extracting data.
- **Trackr table extraction via browser**: When `web_search`/`web_extract` are unavailable (Firecrawl credits exhausted), use `browser_navigate` + `browser_console` with JavaScript to extract table data. Pattern: `document.querySelectorAll('table tr')` → iterate cells → build structured data. This is the reliable fallback for Trackr scraping.
- **eFinancialCareers PIPL block**: eFinancialCareers.fr and .com return 403 "Personal Information Protection Law" pages from some IPs. Use browser-based access or Trackr as fallback.
- **Firecrawl credit exhaustion**: `web_search` and `web_extract` share a credit pool. When exhausted ("Payment Required"), pivot to browser-based extraction of Trackr pages (which are client-side rendered but accessible via browser console). See `references/trackr-browser-extraction.md` for the exact JavaScript pattern.
- **Lazard London off-cycle**: Lazard's London off-cycle program typically opens very early (May-June of the year before) and closes quickly. The Trackr page may show it as CLOSED even if LinkedIn shows live postings — verify directly on `lazard.com/careers` before concluding it's unavailable.
- **US IB program closure rate**: Most bulge-bracket IB summer 2027 programs (Evercore, Moelis, Lazard, PJT, Citizens) closed their first-round applications in Nov 2025 – Feb 2026. Trackr US is the most reliable source for closure status. Do NOT rely on LinkedIn "Actively Hiring" badges — they often remain open after the role is filled.

---

## Verification
- Every presented job must have: Title, Company, Location, Link
- Language: French
- **Output must contain 4 offers per city (12 total): �🇷 Paris, 🇬🇧 London, 🇺� New York**
- Mark source site for each listing
- Mark approaching deadlines with ⚠️

---

## §A — Generic Job Search Web Extraction (formerly job-search-web-extraction)

The technique that powers the Baptiste config — **generalized** for any domain/location.

1. Formulate a web search query combining the job title, location, and site filters (e.g., `entry level finance Paris site:indeed.com OR site:linkedin.com OR site:efinancialcareers.com`).
2. `web_search(..., limit=10-15)` to get a list of relevant job aggregator pages.
3. Select the top 2-3 most relevant result URLs (typically Indeed, LinkedIn, Glassdoor, or domain-specific sites like eFinancialCareers / Wall Street Oasis for finance roles).
4. `web_extract(urls=[...])` on each selected URL to obtain page content in markdown.
5. Parse the extracted content to identify individual job postings (look for tables, lists, or repeated patterns; extract title, company, location, brief description, original URL).
6. Format each job as a bullet point (match output language to requester — French for Baptiste, English otherwise):
   - **Titre / Title**
     Entreprise / Company : …
     Localisation / Location : …
     Description : …
     Lien / Link : …
7. Limit to 5-7 best recent postings; deduplicate by title+company; omit missing salary.

Pitfalls: some sites (Indeed) may block automated requests (try different query); eFinancialCareers loads listings via JS (use `web_search` with `site:efinancialcareers.com`, don't scrape directly); WSO Talent Oasis requires login (note as manual-check site); LinkedIn rate-limits scraping (prefer `web_search` with `site:linkedin.com/jobs`).

Example output: `references/job-extraction-example-job-list.md`.
