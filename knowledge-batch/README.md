# Knowledge document batch proof

Captured in actual Chromium against the candidate Octop React UI, real authentication, HTTP document endpoints, background indexing, SQLite and sidecar vector index. All files and accounts are synthetic. Embedding readiness/vectors and unused agent runtime are stubbed. The browser holds real requests to control the navigation race and injects one destination 500, one list refresh 503 and one document deletion 503. No external model, business data, real provider credentials or third-party services.

- Card/table selection persists across view changes.
- Failed destination navigation leaves the displayed base usable.
- Slow destination navigation permits only the first 3 old-base requests; 5 unsent operations are stopped and old results do not restore the previous base.
- Refresh failures are visible without marking accepted mutations as failed.
- Seven real deletions succeed; one simulated failure stays selected; retry deletes the last real row.
- result.json records the assertions. Screenshots are unedited captures; the synthetic failure toast may still be visible.

This is AI-assisted verification evidence, not a claim that a human manually inspected every source line. Native Windows was not run.
