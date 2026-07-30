---
name: job-search-web-extraction
description: Extract recent job listings from web search results and summarize them in a concise format. Generic extraction technique — for Baptiste's specific config, see baptiste-job-search.
category: research
---

# Job Search Web Extraction Skill

## When to use
When you need to find recent job postings for a given domain and location, and present a short list with title, company, location, description, and link.

**For Baptiste's job search** (finance roles, Paris/London, French output, Telegram delivery): load `baptiste-job-search` instead — it calls this skill's technique with the right parameters.

## Steps
1. Formulate a web search query combining the job title, location, and site filters (e.g., `entry level finance Paris site:indeed.com OR site:linkedin.com OR site:efinancialcareers.com`).
2. Use `web_search` with a limit of 10-15 results to get a list of relevant job aggregator pages.
3. Select the top 2-3 most relevant result URLs (typically from Indeed, LinkedIn, Glassdoor, or domain-specific sites like eFinancialCareers / Wall Street Oasis for finance roles).
4. For each selected URL, call `web_extract` to obtain the page content in markdown.
5. Parse the extracted content to identify individual job postings (look for tables, lists, or repeated patterns containing title, company, location, salary, etc.).
6. For each job, extract:
   - Title
   - Company
   - Location
   - Brief description (1-2 lines summarizing role and key benefits)
   - Application link (the original job posting URL; if not directly available, use the aggregator page link)
7. Format each job as a bullet point (match output language to requester — French for Baptiste, English otherwise):
   - **Titre** / **Title**
     Entreprise / Company : ...
     Localisation / Location : ...
     Description : ...
     Lien / Link : ...
8. Limit the final list to 5-7 best recent postings.
9. Return only the formatted list as the final response.

## Pitfalls
- Some sites (e.g., Indeed) may block automated requests; if blocked, try a different aggregator or adjust query.
- Extracted content may be truncated; ensure you capture enough context to locate job details.
- Duplicate postings across sites; deduplicate by title and company.
- Salary information may be missing; omit if not present.
- **Finance-specific**: eFinancialCareers loads listings dynamically via JS — use `web_search` with `site:efinancialcareers.com`, don't try to scrape the site directly.
- **Wall Street Oasis** (wallstreetoasis.com): Job board ("Talent Oasis") requires login. Don't waste time scraping — note it as a manual-check site instead.
- **LinkedIn**: Heavily rate-limits scraping; prefer `web_search` with `site:linkedin.com/jobs`.

## Verification
- Check that each bullet contains all required fields.
- Ensure links are valid URLs.
- Confirm the output language matches the requester's preference.
- Match output format to delivery channel (Telegram-friendly: no tables, bullet lists).

## Example
See references/example-job-list.md for a sample output.

## Related skills
- `baptiste-job-search` — Baptiste's specific job search config (sites, queries, criteria, tracker)