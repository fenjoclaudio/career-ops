# Scan sources

Used by the "scan" command. Each source says what to look for. Fenjo can add or remove sources with "update".

## How to read a source (try in this order)
1. **Cloud browser** (tools named `mcp__remote-browser__*`), if available. Most career sites below only load properly in a real browser. Decline non-essential cookies.
2. **WebFetch**, for simple pages.
3. **WebSearch** with the site and keywords, for example `site:swp-berlin.org stellenangebot studentische Hilfskraft`. Use this as the fallback for any source that cannot be read, and note in the scan log that only search was possible.

If a source fails with all three methods, log it as `unreachable` in the scan log and move on. Never stop the whole scan because one source fails.

## A. Gmail job alerts (LinkedIn, StepStone, others)
Search Gmail for job alert emails received since the last scan, for example:
`from:(jobalerts-noreply@linkedin.com OR jobs-noreply@linkedin.com OR stepstone) newer_than:5d`
Extract each posting (title, organization, location, link) and evaluate the relevant ones. Do not log in to LinkedIn or any other site. Only use what is in the emails.

## B. Target organizations

| Organization | Where to look | Notes |
|---|---|---|
| Auswärtiges Amt | https://www.auswaertiges-amt.de/de/karriere/praktika/214630-214630 and the AA careers section | Internship program (Praktikant*innenprogramm Inland). Full-time 40 h/week, mandatory internships. Relevant for the Professional Year, not the January phase. Watch for application windows. |
| Bundeskanzleramt | https://www.bundesregierung.de (Stellenangebote), plus Interamt | |
| SWP | https://www.swp-berlin.org/karriere | Regularly posts studentische Hilfskraft roles (20 h/week). Internships listed on the same page when open. |
| McKinsey Berlin | https://www.mckinsey.com/careers/search-jobs (filter Berlin, internships/fellow intern) | Fellow Intern is usually full-time, about 8 to 12 weeks. Berlin office focuses on public sector. |
| Office of a Bundestag MP | WebSearch: `Stellenausschreibung Abgeordnetenbüro Berlin studentische Mitarbeit Auswärtiges OR Verteidigung OR Europa` | Postings are mostly PDFs on MPs' own websites. Focus on MPs on the Foreign Affairs, Defence and European Affairs committees. |
| Rasmussen Global | https://rasmussenglobal.com (Careers page) | Offices in Copenhagen, Brussels and Kyiv, senior staff in Berlin. Often no vacancies. |
| BMVg | https://www.bmvg.de/de/praktikum-im-bmvg, plus Interamt | Abteilung Politik offers internships. |
| BND | https://www.bnd.bund.de (Karriere) | Security screening, long lead times. |
| adelphi | https://careers.adelphi.de/de | Job list is embedded from this portal on adelphi.de/de/karriere. |

## C. Job portals

| Portal | Search |
|---|---|
| Interamt (public sector) | Berlin + Praktikum, studentische Hilfskraft, Werkstudent, together with Auswärtig, Verteidigung, Bundeskanzleramt, Außenpolitik, Sicherheitspolitik |
| Bund.de service portal | Same keywords |
| Think tank job pages (WebSearch) | `site:dgap.org OR site:gppi.net OR site:ecfr.eu OR site:gmfus.org Berlin Werkstudent OR student assistant OR intern` |

## What counts as relevant
Berlin (or remote from Berlin), in German or English, matching one of the two phases in `profile/profile.md`, in think tanks, consultancies, ministries, parliament, international organizations or political strategy. Skip everything clearly outside that (IT, finance, HR, event logistics with no policy content). Count skipped items in the log, but do not create reports for them.
