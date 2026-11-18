# Career-Ops (Fenjo)

My personal job search system, inspired by [santifer/career-ops](https://github.com/santifer/career-ops) and tailored to foreign policy, think tank, consulting and ministry roles in Berlin.

## How to use it
Open a Claude session connected to this repo and do one of the following:

- **Paste a job link or text** → Claude scores it and writes a report
- **"apply"** → tailored CV and cover letter for that posting
- **"status"** → overview of open applications and upcoming deadlines
- **"update ..."** → change the system, for example "weight network higher" or "add GIZ to targets"

Claude never sends applications. I review and submit everything myself.

## What's where
- `CLAUDE.md`: the playbook Claude follows
- `profile/`: my CV, proof points and writing voice
- `config/scoring.md`: how postings are scored
- `targets/organizations.md`: priority employers
- `tracker/applications.md`: every role and its status
- `applications/`: one folder per posting
