# Avsar open feed

Public-sector jobs, project posts and internships read from the official notice pages of
CSIR laboratories in India, as structured data.

**Experimental.** These records are extracted automatically from public notices and have not
been checked by a person. Dates, pay and eligibility can be wrong or missing. Always confirm
against the official notice linked in each record (`links.notice`).

Independent service. Not a government website. We never take fees or applications.

## Files

Served at `https://nt1412.github.io/avsar-feed/v1/`

| File | What it is |
|---|---|
| `manifest.json` | The latest update number, and the SHA-256 of the snapshot and of each recent diff |
| `snapshot.json` | Every record that is open right now |
| `diffs/000001.json` … | One file per update: records added or changed, and records that expired |

A record expires when its last date passes, when a corrigendum cancels it, or when it
disappears from the lab's page on two successful reads in a row.

Each record carries the lab, post title, vacancies, pay, dates, eligibility as structured
rules, a link to the official notice, and the snippet of the notice each key field was read
from. Fields the checker was not sure of are listed in `verification.unsureFields`.

## Reading it

Fetch `manifest.json`. If you have nothing yet, fetch `snapshot.json`. Otherwise apply, in
order, each diff after the update number you already have; if the manifest no longer lists
that chain, fetch the snapshot again.

Licence: not yet chosen.
