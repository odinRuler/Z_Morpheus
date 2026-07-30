# Trackr Browser Extraction — Fallback for Firecrawl Credit Exhaustion

When `web_search` and `web_extract` fail due to Firecrawl credit exhaustion ("Payment Required"), use browser-based extraction of Trackr pages.

## Technique

1. `browser_navigate` to the Trackr URL
2. Click the correct tab (all default to "Summer Internships" — must click "Off-Cycle Internships")
3. Use `browser_console` with JavaScript to extract table data:

```javascript
(() => {
  // Helper to get clean text
  const txt = el => (el?.textContent ?? '').trim();
  
  // Get headers from thead (if present) else assume first row is header
  const headerRows = document.querySelectorAll('table thead tr');
  let headers = [];
  if (headerRows.length) {
    // Use the last thead row as header
    const headerCells = headerRows[headerRows.length - 1].querySelectorAll('th, td');
    headers = Array.from(headerCells).map(txt);
  } else {
    // No thead, assume first tbody row is header
    const firstRow = document.querySelector('table tbody tr');
    if (firstRow) {
      const cells = firstRow.querySelectorAll('td, th');
      headers = Array.from(cells).map(txt);
    }
  }
  
  // If still no headers, fallback to generic indices (adjust per tracker)
  if (headers.length === 0) {
    // Known column indices for each tracker (adjust as needed)
    // This is a fallback; better to detect from page if possible
    return JSON.stringify({error: 'Could not detect table headers'}, null, 2);
  }
  
  // Normalize header names for easier use
  const norm = h => h.toLowerCase().replace(/[^\w]+/g, '_');
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
  
  return JSON.stringify(data, null, 2);
})()
```

## Trackr URLs (as of 2026-06-30)

| Tracker | URL | Notes |
|---------|-----|-------|
| EU Finance Off-Cycle | `app.the-trackr.com/eu-finance/off-cycle-internships` | Defaults to Summer tab |
| France Finance Off-Cycle | `app.the-trackr.com/france-finance/off-cycle-internships` | Defaults to Summer tab |
| UK Finance Off-Cycle | `app.the-trackr.com/uk-finance/off-cycle-internships` | Defaults to Summer tab |
| US Finance 2027 Summer | `app.the-trackr.com/us-finance-2027/summer-internships` | URL changed from `us-finance/` |

## Key Columns (Typical)

### EU/UK/France Off-Cycle
- Status indicator
- Company Name
- Programme Name
- Opening Date
- Closing Date
- Locations (or Locations & Info & Test Prep (France varies)

### US Summer Analyst
- Status indicator
- Company Name
- Programme Name
- Opening Date
- Closing Date
- Latest Stage
- Locations

## Tips

- Always verify you are on the correct tab ("Off-Cycle Internships" for internships, "Summer Internships" for summer roles).
- If the table uses `tbody` but no explicit `thead`, the script above will treat the first `tbody` row as headers; you may need to adjust.
- For site-specific quirks (e.g., merged columns, missing columns), inspect the page and adjust the JavaScript accordingly.
- The script returns a JSON array of objects; you can parse it in your agent code.