# Octop SpreadsheetML knowledge-base integration evidence

Candidate: `feat/knowledge-spreadsheetml` against develop `6ae53c2119d40b032c602d26e1aed7625b733bff`, for issue #1879.

Actual Octop HTTP document upload, background indexing, SQLite, authentication and React dashboard, running in isolated temporary state. Embedding readiness and embedding vectors are synthetic; the unused harness is the repository test fake. No external model, real account or provider credentials are used.

Both cases upload the same synthetic 353-byte Excel 2003 XML file named `orders.xls`, containing a long zero-prefixed Chinese order identifier and `12.25`.

- **Before**: pristine pinned `parse.py` is installed at the existing jobs/service call boundary; the actual job records `failed` with zero chunks and the actual UI displays failure. XLRD reports an unsupported BOF record.
- **After**: candidate parser at the same boundary; actual job records `ready` with one chunk. The real preview API and SQLite vector search both return `# Sales\n订单 0001234567890123456789\t12.25`. Original uploaded bytes are unchanged in both cases.

The JSON files record the actual states and values. Screenshots are unmodified Chromium captures of the real dashboard with those records; they are not generated mockups. All page-error lists are empty. Independent table-origin tests cover offset coordinates; this UI demo uses the default table origin.
