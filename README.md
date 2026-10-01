# academics.iitmandi.ac.in: working copy and proposed updates

This repository holds a copy of the Academic Section website of IIT Mandi
(<https://academics.iitmandi.ac.in>) and the changes proposed to bring it up to date, so that the web
team can review them one at a time.

Maintained by the UG Academic Secretary, IIT Mandi.

## What is on `main`

`main` is the site **as it stands today**, not the updated site:

| Path | What it is |
|---|---|
| `index.html`, `courses.html`, `degreeprograms.html`, … | The 14 pages linked from the main menu, as the server sent them |
| `css/`, `js/`, `images/` | The style sheets, scripts and images the pages load |

Three things differ from the live site, each its own commit:

- links between the pages and to the CSS/JS/images point at this copy, so the site can be browsed locally;
- links to files that are not copied (most PDFs, convocation pages) still open the live site;
- the Google Analytics tag is removed, so previews are not counted as visits.

The CSS, JS and images come from the Wayback Machine copies of the site, because the live server stopped
answering bulk requests. `images/academic/Profile.jpg` was not archived and is missing.

## The proposed changes

The changes are on the branch `update/website-october-2026`, **one commit per change**, and are open as a
single pull request. Its description lists every commit, why the change is needed and what the page looks
like before and after. The branch also carries the documents the new links open, and `docs/` with the full
change document, the audit workbook and the screenshots.

## Viewing a page

```bash
git clone <this repository>
cd academics-iitmandi-website
python -m http.server 8000
```

Then open <http://localhost:8000/>. To see the proposed state, `git switch update/website-october-2026`
and reload; `git show <commit>` shows one change on its own.
