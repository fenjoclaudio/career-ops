# Scan log

Newest scan first. One entry per scan.

Format:
```
## YYYY-MM-DD
Sources checked: n (unreachable: list)
New relevant postings: n (A: n, B: n, C or lower: n)
Skipped as irrelevant: n
Highlights: one line per A or B posting
```

## Seen postings
Every posting the scan has already looked at, so it is never evaluated twice. One line each: `date | organization | title | link | grade or skipped`.
