# Pushup RPG (Android and Seeker): commit ledger

This is a ledger of every commit in the private Android repository of Pushup RPG: Fitness Quest, the codebase that builds both the Google Play app and the Seeker edition on the Solana dApp Store. It lists each commit's hash, dates and size, and nothing else: no code, no file names, no commit messages.

**This ledger is not source code**, and this repository contains none. It is offered as a way to check our work without the source.

## Where the history ends

| | |
|---|---|
| Branch | main, as last fetched from the private remote (read on 2026-09-26) |
| HEAD commit | `749051ebf955f417109b582755c20f35dc0de3e6` |
| HEAD author date | 2026-09-25T16:40:00+05:00 (committer date identical) |
| Commits reachable from HEAD | 576 (573 ordinary commits, 3 merges) |
| First commit | `f58b530acff3178b5556e72264117f5a96784c8d`, 2026-08-11T21:13:33+05:00 |
| Live Seeker APK, 2.5.9-sol (versionCode 65) | built on 2026-09-24 from `9c8df00f663bbd46551bf57a6be2bd2d1c8ddbdb` (a commit dated 2026-09-22T15:48:54+05:00). The APK records this commit id itself: the Android build tools write it into `META-INF/version-control-info.textproto` inside the file, and `unzip -p <apk> META-INF/version-control-info.textproto` prints it. That commit is a row of COMMITS.csv, on main, and the 36 commits after it are not in the APK. |

All author dates carry the offset +05:00 (GMT+5, the same zone as the Clock In deadline). Windows and weeks below use that local date.

## Totals

"Lines" means lines inserted plus lines deleted, summed over ordinary commits. Merge commits are counted as commits but not as lines, because their changes are already counted in the commits they merge. "Solana paths" are files whose path names Solana, Seeker, SIWS or SOL (see *Area tags*).

| Window | Commits | of which merges | Inserted | Deleted | Lines | Commits touching Solana paths | Lines on Solana paths |
|---|---:|---:|---:|---:|---:|---:|---:|
| Whole history (2026-08-11 → 2026-09-25) | 576 | 3 | 323,613 | 33,356 | 356,969 | 24 | 5,248 |
| Whole history minus the baseline import | 575 | 3 | 216,334 | 33,356 | 249,690 | 23 | 3,677 |
| Before 2026-09-08 | 362 | 0 | 244,434 | 22,907 | 267,341 | 3 | 1,624 |
| **Clock In window: 2026-09-08 → now** | **214** | 3 | 79,179 | 10,449 | **89,628** | 21 | 3,624 |
| **Colosseum window: 2026-09-14 → now** | **179** | 3 | 56,570 | 9,778 | **66,348** | 21 | 3,624 |
| Seeker build week: 2026-09-18 → now | 74 | 0 | 19,016 | 4,200 | 23,216 | 21 | 3,624 |

"Now" is HEAD, 2026-09-25. Every commit that touched Solana paths inside either hackathon window falls on or after 2026-09-18.

### What the line counts are made of

Line counts measure volume, not quality, and they include data as well as code.

| Kind of file | Whole history | since 2026-09-08 | since 2026-09-14 | since 2026-09-18 |
|---|---:|---:|---:|---:|
| Kotlin source (including the Gradle build scripts) | 249,143 | 57,758 | 49,681 | 19,369 |
| Android resource files (layouts, strings, translations) | 42,933 | 18,132 | 6,490 | 1,864 |
| Data files (translation tables, test fixtures, release notes) | 50,022 | 9,294 | 7,687 | 272 |
| Server functions, database migrations and scripts | 6,494 | 3,555 | 1,785 | 1,255 |
| Documentation | 4,160 | 718 | 599 | 350 |
| Other (build configuration and similar) | 4,217 | 171 | 106 | 106 |
| **Total** | **356,969** | **89,628** | **66,348** | **23,216** |

Binary files such as images are counted in `files_changed` and `binary_files` but add no lines.

## Disclosure: work that predates both hackathons

- **The history starts with an import.** The first commit (2026-08-11) adds 563 files and 107,279 lines in one step. The Android app was written before this repository's history begins: from about July 2026, and the iOS app from 2026-06-01. That earlier history is not in this repository.
- **The import already contained a Solana edition.** 12 of those files (1,571 lines) sit on Solana paths: a Solana build flavor with wallet sign-in, server functions that verify a Sign-In-With-Solana signature and a SOL payment, a database schema for them, and a design note. One of those files carries the date 2026-06-22 in its own name. The history cannot show when that work was written. It can only show that it existed by 2026-08-11.
- **Between the import and the hackathons**, 2 more commits touched Solana paths (53 lines, week of 2026-08-31).
- **During the hackathons**, 21 commits between 2026-09-18 and 2026-09-25 changed 3,624 lines on Solana paths. This is the work that took the Seeker edition to a live release: the Seeker edition was first submitted to the Solana dApp Store on 2026-09-20 and has been live since 2026-09-24. Seeker-related changes made in code shared by both editions are tagged `app` below. They are not counted as Solana lines, so the 3,624 is a floor for Seeker work in that week, not a ceiling.
- The game itself (camera rep counting, campaign, duels, guilds, leaderboards) predates both windows. The 214 and 179 commits in the windows are continued work on an existing, shipping product.

## Per week

Weeks run Monday to Sunday, GMT+5.

| Week starting | Commits | Lines | Commits touching Solana paths | Lines on Solana paths | Note |
|---|---:|---:|---:|---:|---|
| 2026-08-10 | 56 | 125,543 | 1 | 1,571 | includes the baseline import (107,279) |
| 2026-08-17 | 59 | 35,984 | 0 | 0 | |
| 2026-08-24 | 141 | 17,703 | 0 | 0 | |
| 2026-08-31 | 99 | 77,419 | 2 | 53 | |
| 2026-09-07 | 42 | 33,972 | 0 | 0 | Clock In window opens 2026-09-08 |
| 2026-09-14 | 135 | 53,890 | 17 | 3,597 | Colosseum opens 2026-09-14; 3 merges; Seeker work from 2026-09-18 |
| 2026-09-21 | 44 | 12,458 | 4 | 27 | through HEAD, 2026-09-25 |
| **Total** | **576** | **356,969** | **24** | **5,248** | |

## Area tags

Each commit gets one `area` tag, taken from the paths it changes: the area with the most changed lines in that commit wins, and file count breaks ties.

- **seeker**: the Solana build flavor and its tests, and the Solana backend (wallet sign-in and SOL payment verification functions, and their database schema).
- **app**: the Android app's own source and resources, shared by the Play and Seeker editions (including debug-only builds).
- **backend**: other server-side work: database migrations, server configuration, deployment and database scripts.
- **tests**: unit tests, test fixtures and test tooling.
- **docs**: written documentation, release notes and store-listing assets.
- **build**: build configuration, the build wrapper, and development tooling.

Commits by area (ordinary commits only):

| Window | seeker | app | backend | tests | docs | build |
|---|---:|---:|---:|---:|---:|---:|
| Whole history | 13 | 202 | 4 | 295 | 17 | 42 |
| since 2026-09-08 | 12 | 61 | 0 | 117 | 9 | 12 |
| since 2026-09-14 | 12 | 48 | 0 | 102 | 7 | 7 |
| since 2026-09-18 | 12 | 24 | 0 | 33 | 2 | 3 |

`tests` leads because most changes land with tests that are longer than the change itself. One tag per commit hides mixed commits, so every row of COMMITS.csv also carries `seeker_files` and `seeker_lines`. A commit tagged `app` that also touched Solana paths shows it there. That is why 24 commits touch Solana paths while only 13 are tagged `seeker`.

## COMMITS.csv columns

One row per commit reachable from HEAD, 576 rows, oldest first.

| Column | Meaning |
|---|---|
| `commit` | full 40-character commit hash |
| `author_date` | when the change was authored, ISO 8601 with offset |
| `committer_date` | when it was last committed. This differs from `author_date` on 20 commits, which were rebased or amended |
| `merge` | 1 for the 3 merge commits, else 0 |
| `files_changed` | number of files changed (a count only) |
| `insertions`, `deletions` | lines added and removed. For a merge, measured against its first parent and excluded from the totals above |
| `binary_files` | how many of the changed files are binary (no line counts) |
| `area` | one of seeker, app, backend, tests, docs, build |
| `seeker_files`, `seeker_lines` | how many changed files, and how many changed lines, are on Solana paths |

## What a commit hash proves

A commit hash is a SHA-1 fingerprint of the commit itself. It covers the exact contents of every file in the repository at that commit (through the tree hash), the hash of its parent commit or commits, the author and committer names, e-mail addresses and dates, and the commit message. Changing a single byte of any file, any date, or any earlier commit gives a different hash. Because every commit contains its parent's hash, the HEAD hash above fixes the entire 576-commit history behind it. The fingerprint is one-way, so publishing these hashes reveals nothing about the code. That makes this ledger a commitment made now. Later, in a live screen-share of a terminal in the private repository, a judge can pick any listed commit and have git print its hash, dates and line counts with `git show --shortstat --diff-merges=first-parent --format='%H %aI %cI' <hash>`, and the total with `git rev-list --count 749051e`, and see that they match the row here. That command prints no code, no file names and no commit message. It shows that the content existed in exactly that form and order no later than the date this ledger was submitted. In a screen-share the judge is reading output on the owner's screen, so it is a weaker check than running git on a copy of the repository, which we do not share. A hash does not prove when the code was written: the dates inside a commit come from the author's own machine and can be set by hand. So the ledger proves content and order, and the submission timestamp of the ledger itself is the independent upper bound on time. Git uses a collision-hardened form of SHA-1.
