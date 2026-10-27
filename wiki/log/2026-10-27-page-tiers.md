## [2026-10-27] ingest | Page tiers for existing pages, record removed as a source

Raw slugs: `26-10-27-1138-wiki-pr52-page-tiers`

Pages touched:
- all 51 existing pages (status unchanged). PR 56 set tier on each: 43 tool pages volatile, 5 method and 3 synthesis pages core, and cited the PR-52 record as a source. Both second-opinion reviews called that record a non-source that inflates source counts, so this change removes it from every page's sources, restores each page's previous updated stamp (the tier fields are metadata, not a content refresh) and gives the 43 tool pages separate review_by dates (2027-01-11 to 2027-02-22) instead of one shared date.

Note: the raw record stays (raw is add-only) but no page cites it. confidence is still unset on every page.

Commit: see the PR
