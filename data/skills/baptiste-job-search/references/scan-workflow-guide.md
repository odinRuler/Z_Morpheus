# Scan Workflow Guide

## Execution Pattern (Parallel)

For fastest results, use `delegate_task` with 3 parallel workers per city. Each worker:
1. Runs 8-10 `web_search` queries against the city-specific sources
2. Extracts details from promising URLs via `web_extract`
3. Returns structured results

## Output Checklist (per scan file)
- [ ] 4 offers per city (12 total)
- [ ] Each offer has: Title, Company, Location, URL
- [ ] Duration and start date noted
- [ ] ⚠️ on approaching deadlines
- [ ] "Nouveautés" comparison table vs previous scan
- [ ] Saved to `references/scan-YYYY-MM-DD.md`

## Paris Priority Sources (in order)
1. Rothschild careers page (multiple divisions)
2. Ardian join-us / Workday
3. Jefferies.tal.net
4. eFinancialCareers.fr/.com
5. Trackr EU
6. Indeed.fr (French queries)
7. KKR careers
8. Blackstone careers

## London Priority Sources (in order)
1. Blackstone campus careers (multiple divisions)
2. eFinancialCareers.co.uk Jefferies, Baird, Lincoln, CVC, Goldman Sachs, Macquarie, Evercore)
3. Goldman Sachs higher.gs.com
4. KKR careers
5. Trackr UK

## NYC Priority Sources (in order)
1. eFinancialCareers.com (Bridgewater, Cantor, D.E. Shaw, Cantor, Stephens, etc.)
2. Insight Partners, Lead Edge Capital
3. Bridgewater, Waterfall, Cantor Fitzgerald direct pages
4. Goldman Sachs (gs.com/careers)
5. Trackr US (via web_search fallback)

## Deadline Hotspots (as of June 2026)
- Blackstone PE Summer (London + NYC): closes 29 Oct 2026
- **Goldman Sachs 2027 Summer Analyst (Americas)**: applications open **August 15, 2026** — do NOT trust third-party aggregators which claim a Jan/Feb deadline (wrong year)
- Goldman Sachs EMEA off-cycle: rolling, 4 apps/year cap — always verify on higher.gs.com
- KKR: rolling, apply ASAP
- Jefferies: opened 10 Jun  2026
- Bridgewater: very competitive, multi-round
- US IB programs (Evercore, Moelis, Lazard, PJT, Citizens): **mostly CLOSED** for 2027 summer — Trackr US confirms status
- Point72 Academy: rolling admissions, ONE application globally — apply to preferred region only
