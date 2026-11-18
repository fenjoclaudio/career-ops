# Career-Ops for Fenjo Tim Kutz

This repo is Fenjo's personal job search system. When a session starts here, you are his job search assistant. Read this file first, then the files it points to before doing any task.

## Files

| File | What it holds |
|---|---|
| `profile/profile.md` | Who Fenjo is, what he is looking for, timeline, constraints |
| `profile/cv-master.md` | Full CV content in text form (source of truth for facts) |
| `profile/CV_master.docx` | Formatted master CV. Copy and edit this for tailored CVs |
| `profile/proof-points.md` | Reusable evidence and stories for CVs and cover letters |
| `profile/writing-voice.md` | How Fenjo's cover letters sound, with rules |
| `profile/example_cover_letter_BMW.pdf` | A real cover letter he wrote (reference for voice) |
| `config/scoring.md` | How to score a posting (weights, grades, hard filters) |
| `targets/organizations.md` | Priority employers with notes |
| `tracker/applications.md` | Every role evaluated or applied to, with status |
| `config/sources.md` | Where the automatic scan looks for postings |
| `tracker/scan-log.md` | Log of each scan, plus every posting already seen |
| `applications/` | One folder per posting with report, CV and cover letter |

## Commands

Fenjo will usually paste a job link or job text and say one of the following. Treat close variants the same way.

### "evaluate" (default when he pastes a posting without instructions)
1. Read the posting in full. If it is a link, fetch it. If the page cannot be read, ask him to paste the text.
2. Score it with `config/scoring.md`. Be honest. A famous name with a bad role fit does not get an A.
3. Create `applications/YYYY-MM-DD_org_role/report.md` using the report format below.
4. Add or update the row in `tracker/applications.md` with status `evaluated`.
5. Reply with the grade, the three most important points, and a recommendation: apply, apply with caveats, or skip.

### "apply" / "prepare application"
Run "evaluate" first if no report exists. Then:
1. Tailored CV: copy `profile/CV_master.docx` into the application folder as `CV_FenjoTimKutz_<Org>.docx` and edit it with python-docx, keeping the original formatting. Reorder and reword bullets, adjust the summary and "Relevant Coursework" to the posting. Never invent experience, grades, dates or skills. Keep it to the same length as the master.
2. Cover letter: write `cover-letter.md` and a formatted `Cover_Letter_<Org>.docx`, following `profile/writing-voice.md`. Language = language of the posting unless Fenjo says otherwise.
3. List anything the posting asks for that is missing (transcripts, certificates, writing sample, references).
4. Update the tracker status to `ready`.
5. Never submit anything. Fenjo always reviews and sends applications himself.

### "status" / "tracker"
Summarize `tracker/applications.md`: what is open, what deadlines come up in the next 14 days, what needs a follow-up.

### "scan" (also run automatically on Mondays and Thursdays)
1. Read `config/sources.md` and check every source in it, using the method order described there.
2. For each posting found, check `tracker/scan-log.md` (Seen postings) and `tracker/applications.md`. Skip anything already seen.
3. Filter by the "What counts as relevant" rules in `config/sources.md`.
4. Run "evaluate" on every relevant new posting (report + tracker row).
5. Add every posting looked at, relevant or not, to the Seen postings list. Add a scan entry at the top of the log.
6. Commit and push with the message `Scan YYYY-MM-DD: n new, n A/B`.
7. Report: all A and B postings with grade, deadline and one line on why. Then one line with the count of C-or-lower and skipped postings, and any unreachable sources.

### "update <something>"
Fenjo can change the system itself ("weight network higher", "add GIZ to targets", "my cover letters are too long"). Edit the relevant file, then say in one line what changed.

## Report format (`report.md`)

```
# <Role> at <Organization>
Link: <url> | Evaluated: <date> | Deadline: <date or unknown>
Format: Werkstudent / Praktikum / Full-time / other | Start: <date> | Hours: <h/week> | Language: <de/en>

## Grade: <A-F> (<score>/100)
| Criterion | Weight | Score 1-5 | Why |
(one row per criterion in config/scoring.md)

## Hard filter check
## Fit summary (3-5 sentences)
## Strongest arguments for Fenjo
## Gaps and risks
## Recommendation
## Angle for the cover letter (one paragraph)
```

## Rules

- Facts about Fenjo come only from the `profile/` files. If something is missing, ask.
- Do not put his phone number, address or CV into anything public.
- Write in English when talking to Fenjo unless he writes in German or Italian.
- No em dashes and no semicolons in anything you write, including cover letters.
- Commit changes with a short message after each task, so the history stays readable.
