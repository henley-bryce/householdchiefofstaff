# Tool limits

Things that look doable but commonly are not. Verify each against the tools actually connected, because connectors change. If a tool is missing or fails, say so plainly and offer the manual path.

## Hub tool

- **Google Docs/Drive**: many Drive connectors can create and trash files but **cannot edit an existing file in place**. "Updating" means delete and recreate, which changes the link every time and loses anything the partner added. Do not use this as a shared living hub unless a real doc-editing tool is available.
- **Notion** (or any tool with in-place page edits): the best fit for a shared living page. Edits keep the same link. Table and checklist syntax can be finicky; when an edit fails on a match, fetch the page again and copy the exact text, including indentation.
- **Sharing**: most connectors cannot invite another person. The user has to share the page with their partner themselves.

## Spreadsheets

- Drive connectors typically read computed values only, not formulas, and cannot write a single cell. Do not promise automated cell updates. If the user wants "invoices from email into a sheet," confirm that a tool with real cell-level write access exists first.
- Converting an uploaded .xlsx to a Google Sheet through a connector can fail intermittently. If it does, offer the raw file and have the user use Drive's own "Open with Sheets."
- Spreadsheet comments can break files after a recalculation pass in some environments. Prefer notes in a visible cell.

## Email

- Reading and labeling work. **Creating inbox filters** (auto-label and skip inbox for future mail) is often not available through the connector. The assistant can label and mark-read existing mail, but the user should create the native filter themselves for new mail.
- School apps often have no parent-facing API. Switch their notifications to email and read the email.

## Calendar

- Reading a partner's calendar works best by having them share or publish it once, then subscribing it into the user's calendar. Some work calendars cannot be published; ask before assuming.

## Scheduled tasks

- Not every environment can create them. If this one cannot, give the user the prompt and the place to paste it. Never claim a recurring job exists unless creation actually succeeded.
- A scheduled task runs in a fresh session with no memory of the chat. Its prompt must be fully self-contained.

## Sensitive data

- Do not copy credentials, account numbers, or financial detail into the hub. If the user's existing documents contain plaintext credentials, tell them directly and suggest a password manager.
