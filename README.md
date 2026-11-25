# sidequest

A skill for Claude Code: what to do when the work wanders off the main task.

A side quest is an idea, an experiment, a research question, a demo or a spin-off that turns up in the middle of
something else. Some stay research. Some become a feature the same day. One might become its own app. This skill
makes Claude treat each one like a branch in development:

1. **Bookmark the main quest** - what was in progress and what it was waiting on.
2. **Keep the side quest separate** - its own git branch or its own folder.
3. **Write it down** - one line in a ledger, one note per quest, with a status:
   open, parked, done, graduated or dropped.
4. **Come back** - say where the main quest stands when the side quest stops.

## Where it came from

This skill is itself a side quest. It was born in the middle of other work, on a day when three unplanned side
quests had already paid off, as a fourth: "we should have a way to handle these". It was bookmarked, kept separate,
written down and graduated by the rules it describes, and it is a line in its own ledger.

## Install

```bash
git clone https://github.com/dopamine10/sidequest ~/.claude/skills/sidequest
```

The skill triggers on "side quest" / "sidequest" in any form. To make sure it applies on every project, add a short
pointer to `~/.claude/CLAUDE.md`:

```md
## Side quests
When the user says "side quest" in any form, or the work clearly leaves the main task for an idea, experiment,
research question, demo or spin-off, use the `sidequest` skill.
```

## Where things live

| What | Where |
|---|---|
| The skill | `SKILL.md` (this folder) |
| The ledger | `~/.claude/sidequests/INDEX.md` - one line per quest, every project |
| One note per quest | `~/.claude/sidequests/<date>-<slug>.md` |
| Starting files for a new ledger | `templates/` |
| What using it has taught | `FIELD-NOTES.md` |

The ledger is NOT part of this repo: it holds the details of whatever projects the quests came from.

## Status

Young (first written 2026-11-25, public the same day). It changes as it is used; `FIELD-NOTES.md` is where the reasons go.

## License

MIT: use it, change it, share it. See `LICENSE`.
