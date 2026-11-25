---
name: sidequest
description: Handle a side quest on any project on this machine - an idea, experiment, piece of research, demo, video or spin-off that branches away from the work in progress. Bookmarks the main quest, keeps the side quest's work separate like a git branch in development, records it in a ledger with a status (open, parked, done, graduated, dropped), and returns to the main quest afterwards. Use when the user says "side quest" or "sidequest" in any form ("OMG another side quest", "NOTE: THIS IS A SIDEQUEST", "quick side quest"), asks to list, resume, park, graduate or drop one, asks "what side quests do we have", or when work clearly leaves the main task for something the user did not plan.
---

# Side quests

Side quests pay off again and again: a demo page becomes a website feature in one morning, a question about someone
else's post becomes a research note. A side quest may stay research, become a feature, or become a new app. Treat each
one as **a branch in development**: welcome, separate from the main work, written down, and easy to come back to.
Never talk the user out of one, and never let one silently replace the main quest.

Ledger: `~/.claude/sidequests/INDEX.md` (one line per quest, every project) and one note per quest beside it.

## When one starts

1. **Bookmark the main quest** in one or two lines: what was in progress, what is waiting on whom, anything left in
   a live state (phones mid-test, a server running, a branch half-edited). Put it in the quest's note.
2. **Open the note**: `~/.claude/sidequests/<YYYY-MM-DD>-<slug>.md` from the template below, and add its line to
   `INDEX.md`. Do this at the start, not at the end: a quest that is interrupted must still be findable.
3. **Say it in one line** to the user: that this is logged as a side quest, and what the main quest is paused on.
   Then do the quest. No ceremony beyond that.

## While it runs

- **Keep its work separate.**
  - Code in a repo: a branch `sidequest/<slug>` (or a worktree) off the current work. Never commit side-quest
    changes into the main quest's commits. If the user asks for the change to go live right away (a site update they
    want published), do that on the project's normal branch as its own commit and record it as graduated.
  - Everything else (research, prototypes, renders, mockups): its own folder. Use the project's scratch area if it
    has one (a gitignored `workspace/` or `scratch/` folder: `<that>/sidequests/<slug>/`), else `~/sidequests/<slug>/`.
- **The project's own rules still apply**: commit style, no pushing without an ask, privacy, release notes,
  confirmation before anything outward-facing.
- **Size it honestly.** A question gets an answer and a short note. Do not turn a question into a build unless asked; say what the cheapest next step would be and leave it there.
- **Nested side quests** are separate quests: each gets its own note and line.

## When it stops

1. **Set the status** in the note and in `INDEX.md`:
   - `open` - still being worked on
   - `parked` - stopped on purpose; the note says the next step and what it would take
   - `done` - a one-off that is finished (an answer, a video, a clip)
   - `graduated` - became real: a feature, a live page, a new project. Say where it lives now (commit, URL, repo)
   - `dropped` - tried and not worth it; the note says why, so it is not re-proposed blind
2. **Fill in the note**: what was made and where (paths, URLs, commits, branches), what was learned, what it could
   grow into, the next step if picked up again.
3. **Return to the main quest out loud**: one line restating where the main quest stands and what it is waiting on.
   If the side quest changed anything the main quest depends on, say so.
4. If the project has its own memory or handoff notes, add a pointer there only when the quest changed that
   project's state (something shipped, a rule changed). The ledger is the record of the quest itself.

## Other requests

- **"What side quests do we have" / list**: read `INDEX.md`; show open and parked first, newest first, as a short table.
- **Resume**: read the quest's note, restate the bookmark and the next step, continue in its branch or folder.
- **Graduate**: move the work to where it belongs (merge or cherry-pick the branch on the user's word, or start the new
  project), then mark it `graduated` with the new home.

## Improving this skill

This folder is its own git repo (see README.md). When handling a side quest shows a gap or a rule that did not fit,
add a dated line to `FIELD-NOTES.md` here, say so, and propose the change to the skill. Commit skill changes in this
repo; push only when asked.

## Note template

```md
# <Title>

- **Started:** <YYYY-MM-DD>, in <project / folder>
- **Status:** open | parked | done | graduated | dropped
- **Sparked by:** <what set it off - the user's own words if there were any>
- **Main quest paused at:** <what was in progress and what it was waiting on>

## What it is
<two or three sentences>

## What was made
<paths, URLs, commits, branches>

## What was learned
<facts worth keeping; mark what was measured and what is a guess>

## Where it could go
<research only / a feature / its own app - and the cheapest next step>
```

## INDEX.md line

`| <date> | <project> | <title> | <status> | <one line: what it is and where it lives> | [note](<file>.md) |`
