# academics.iitmandi.ac.in: working copy and proposed updates

This repository holds a copy of the Academic Section website of IIT Mandi
(<https://academics.iitmandi.ac.in>) and the changes proposed to bring it up to date.
Each change is its own commit on one branch, open as a single pull request, so the web team can review,
keep or drop them one at a time.

Maintained by the UG Academic Secretary, IIT Mandi.

## What is on `main`

`main` is the site **as it stands**, not the updated site:

| Path | What it is |
|---|---|
| `index.html`, `courses.html`, `degreeprograms.html`, … | The 14 pages linked from the main menu, as the server sent them |
| `css/`, `js/`, `images/` | The style sheets, scripts and images the pages load |
| `docs/Academics_Website_Updates.pdf` | The full change document: every change with its location, screenshots, commit and code |
| `docs/Academics_Website_Audit.xlsx` | The audit workbook (page issues, broken links, course-table lists) |
| `docs/course_table_changes.csv` | Every row to add, mark or correct in the course table |
| `docs/screenshots/` | Before/after screenshots used in the pull requests |

Three things differ from the live site, and each is its own commit on `main`:

- links between pages and to the CSS/JS/images point at this copy, so the site can be browsed locally;
- links to files that are not copied (most PDFs, convocation pages) still open the live site;
- the Google Analytics tag is removed, so previews are not counted as visits.

The CSS, JS and images come from the Wayback Machine copies of the site, because the live server stopped
answering bulk requests during the check. `images/academic/Profile.jpg` was not archived and is missing.

## Viewing a page

```bash
git clone <this repository>
cd academics-iitmandi-website
python -m http.server 8000
```

Then open <http://localhost:8000/>. The branch `update/website-october-2026` has the proposed state; `git switch` to it and reload the page.

## The changes

The pull request describes each problem, shows the page before and after, lists the sources (UG Ordinance 2026,
UG Handbook 2026, the UG Curriculum booklet, BoA/Senate minutes) and says how to check each change.
`git show <commit>` shows one change on its own.

| ID | Commit | Page | Change |
|---|---|---|---|
| S1 | `7491e77` | Every page | Footer quick links that give "404 Not Found" |
| S2 | `3177d11` | Every page | Footer phone link dials a different number |
| S3 | `668e55b` | Every page | Copyright year is 2024 |
| S4 | `4e82a8e` | Every page | "Research" menu item opens the home page |
| S5 | `2f20c01` | Every page | Ordinances page is not in the menu |
| H2 | `e3d96db` | Home | Announcements are from the previous admission cycle |
| C1 | `b8dfaac` | Courses | Course booklet is the June 2025 compilation |
| C9 | `cb2eb96` | Courses | Section 2: old grading system shown as the current one |
| C2 | `06cb730` | Courses | Section 3 "Common Core" shows the curriculum of 2016-2022 |
| C3 | `76f08ef` | Courses | Section 4 "Humanities Course Basket" stops at February 2020 |
| C4 | `efb651e` | Courses | Section 5 "Design and Innovation Practicum": old courses and a dead link |
| C5 | `037ac56` | Courses | Section 6 "Minor Program": five minors missing, Robotics core out of date |
| C6 | `377393e` | Courses | Section 7 "Double Major Programme": one paragraph from 2021 |
| C8 | `5472c55` | Courses | New section 9: Mutually Exclusive Courses |
| C7c | `87697f1` | Courses | Course table: old and misspelt titles |
| C7b | `aa7d4af` | Courses | Course table: 43 codes listed more than once |
| C7a | `7847f87` | Courses | Course table: recoded, discontinued or never-approved courses |
| C7d | `d9727a5` | Courses | Course table: 578 approved courses are missing |
| C7e | `22ee465` | Courses | Course table: two code styles (BE-203 and BE203) |
| D1 | `be69566` | Degree Programs | UG programme list: mixed old and 2023 curricula, nothing for 2024-2026 |
| O1 | `e67b386` | Orientation | Orientation fee table: payment date says 2025 |
| O2 | `8253a30` | Internships | Internships: SHSS list links the 2025 file |
| O3 | `dae3d49` | Ordinances | Ordinances page: UG Ordinance 2026 is missing |
| O4 | `70e46ab` | Scholarships | Scholarships page: no eligibility rules, and broken table rows |

Two points need the office's input and are open as issues instead:

- **H1**: Staff list: "Nikhil Kumar" appears twice
- **D2**: PhD and some PG programmes have no curriculum link

## Documents added by the changes

Some pull requests add the documents that their new links open:

| File | Source | Added by |
|---|---|---|
| `pdf/ordinances/UG_Ordinance_2026.pdf` | UG Ordinance 2026 | H2, C9, C2, C6, O3 |
| `pdf/admissions/UG_Curriculum_Batch2023-2026.pdf` | UG Curriculum booklet, batches 2023–2026 (BoA annexure) | C2, D1 |
| `pdf/courses/minors/<MINOR>.pdf` | One course basket per minor (20 files), cut from the Minors booklet (BoA annexure) | C5 |
| `pdf/courses/Mutually_Exclusive_Courses.pdf` | Mutually Exclusive Courses booklet (BoA annexure) | C8 |
| `files/IIT_Mandi_Course_Descriptions_2026.pdf` | Master Compilation of Courses (all BoA/Senate minutes) | C1 |
| `pdf/senate_courses/<CODE>.pdf` | One syllabus per course, cut from the Master Compilation | C2, C7 |

The three booklets were placed before the 66th BoA. They should go on the live site only after approval.

## Points to confirm

While preparing the changes, some differences turned up between the UG Ordinance 2026, the UG Handbook 2026,
the UG Curriculum booklet and the minutes, for example the Discipline Core/Elective split of seven branches and
the MTP and internship course codes. They are listed in Appendix F of `docs/Academics_Website_Updates.pdf`.
