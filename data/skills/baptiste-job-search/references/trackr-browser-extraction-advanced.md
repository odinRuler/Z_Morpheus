# Advanced Trackr Browser Extraction — Filtering and Sorting

When `web_extract` fails due to Firecrawl credit exhaustion, you can use browser-based extraction with custom JavaScript to not only pull the raw table but also filter for relevant roles (Private Equity, M&A, Investment Banking, Hedge Fund) and/or those containing "2027", then sort by opening date (most recent first) and limit to the top 4.

## Usage

1. Navigate to the Trackr page (e.g., `app.the-trackr.com/france-finance/off-cycle-internships`).
2. Ensure you are on the correct tab (click "Off-Cycle Internships" if needed).
3. Run the following JavaScript via `browser_console`:
4. The result will be a JSON array of up to 4 objects, each containing:
   - company, company_link
   - programme, programme_link
   - opening, closing
   - (optional) locations, etc., depending on the table columns.

## JavaScript Snippet

```javascript
(() => {
  // Month mapping for date parsing
  const months = {"Jan":"01","Feb":"02","Mar":"03","Apr":"04","May":"05","Jun":"06","Jul":"07","Aug":"08","Sep":"09","Oct":"10","Nov":"11","Dec":"12"};
  function parseDate(dateStr) {
    if (!dateStr) return "00000000";
    const parts = dateStr.split(' ');
    if (parts.length !== 3) return "00000000";
    const day = parts[0].padStart(2, '0');
    const month = months[parts[1]];
    const year = "20" + parts[2];
    return year + month + day;
  }

  // Helper to get clean text
  const txt = el => (el?.textContent ?? '').trim();

  // Determine headers (try thead, else first tbody row)
  let headers = [];
  const headerRows = document.querySelectorAll('table thead tr');
  if (headerRows.length) {
    const headerCells = headerRows[headerRows.length - 1].querySelectorAll('th, td');
    headers = Array.from(headerCells).map(txt);
  } else {
    const firstRow = document.querySelector('table tbody tr');
    if (firstRow) {
      const cells = firstRow.querySelectorAll('td, th');
      headers = Array.from(cells).map(txt);
    }
  }

  // Normalize header names for easier matching
  const norm = h => h.toLowerCase().replace(/[^\\w]+/g, '_');
  const normHeaders = headers.map(norm);

  // Extract rows from tbody
  const rows = Array.from(document.querySelectorAll('table tbody tr'));
  const data = rows.map(row => {
    const cells = row.querySelectorAll('td');
    const obj = {};
    normHeaders.forEach((h, i) => {
      if (cells[i]) obj[h] = txt(cells[i]);
    });
    return obj;
  });

  // Filter for relevant roles
  const filtered = data.filter(item => {
    const prog = (item.programme_name || item.programme || '').toLowerCase();
    const comp = (item.company_name || item.company || '').toLowerCase();
    const isRelevant =
      prog.includes('private equity') ||
      prog.includes('pe') ||
      prog.includes('m&a') ||
      prog.includes('investment banking') ||
      prog.includes('ib') ||
      prog.includes('hedge fund') ||
      prog.includes('hf') ||
      prog.includes('2027') ||
      comp.includes('private equity') ||
      comp.includes('pe') ||
      comp.includes('hedge fund') ||
      comp.includes('hf');
    return isRelevant;
  });

  // Sort by opening date descending (most recent first)
  filtered.sort((a, b) => parseDate(b.opening) - parseDate(a.opening));

  // Return top 4
  const top4 = filtered.slice(0, 4);
  return JSON.stringify(top4, null, 2);
})()
```

## Notes

- Adjust the field names (`programme_name`, `company_name`, `opening`, `closing`) if your table uses different column headers; the script uses the normalized header names derived from the table's header row.
- If the table does not have a `<thead>`, the script assumes the first `<tbody>` row contains headers and skips it in data extraction.
- The filter condition includes both programme and company fields to catch cases where the company name indicates the sector (e.g., "KKR").
- The date parsing assumes dates are in the format "DD Mon YY" (e.g., "23 Jun 26"). Adjust if your locale differs.
- The returned JSON can be parsed in your agent code to produce the final output.