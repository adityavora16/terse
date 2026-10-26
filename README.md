# Terse

**Claude Code answers in the first sentence and stops when the answer is complete.**

Terse is a free Claude Code skill. It cuts the preamble, the restated question, the recap of finished
work and the closing offer, then strips the common AI writing tells (stock vocabulary, em dashes,
staccato fragments, aphorisms) from the words that stay.

It is not a word limit. When an answer depends on a condition, when something is destructive or
risky, or when a task failed, Terse keeps the extra sentence. Code, config, file contents, commit
messages and documents you asked for are never shortened.

## Before and after

**Question:** Does `Array.prototype.sort` sort numbers numerically by default?

**Before**

> Great question! This is a common point of confusion in JavaScript. By default, the `sort`
> method converts the elements to strings and compares them in UTF-16 order, which means numbers
> are not sorted numerically. For example, `[10, 9, 1].sort()` returns `[1, 10, 9]`. If you want a
> numeric sort, you can pass a comparison function. I hope this helps! Let me know if you would
> like me to walk through how comparison functions work.

**With Terse**

> No. It sorts as strings, so `[10, 9, 1]` becomes `[1, 10, 9]`. Pass `(a, b) => a - b`.

Five more pairs (a which-one, a why-is-it-broken, a how-do-I, a finished code change, a multi-part
answer) are in [`samples/before-and-after.md`](samples/before-and-after.md).

## Install

Needs Claude Code 2.1.116 or newer. Nothing else: no script, no dependencies.

```bash
claude plugin marketplace add adityavora16/claude-plugins
claude plugin install terse@adityavora
```

Start a new session and type `/terse:terse`, or ask in plain words: "keep it short", "just tell
me", "one line". Inside a session, `/plugin marketplace add` and `/plugin install` do the same.

Other ways in (copy the skill folder, or load it for one session) are in [`INSTALL.md`](INSTALL.md).

## How it works

1. Claude answers in the first sentence and stops when the answer is complete.
2. Each kind of question has a budget: one sentence for a yes/no, the pick and one clause of why for
   a which-one, cause and fix for a why-is-it-broken, the command for a how-do-I, one line per file
   for a finished change, one line per part for a multi-part answer. Over budget is a signal to cut,
   not a hard cap.
3. Five cases break brevity on purpose: something destructive, a risk you have not seen, a task
   that failed or was partly skipped, an answer that depends on a condition, and a request to be
   taught.
4. The words that survive are checked against a list of AI writing tells. The skill watches hardest
   for the four that brevity itself causes: staccato drama, aphorism, tailing negation and
   subjectless fragments.

## What is in the repo

| Path | What it is |
|---|---|
| `skills/terse/SKILL.md` | the skill: the rule, what to cut, the budgets, when to break brevity, the voice rules |
| `skills/terse/references/ai-tells.md` | the full checklist of AI writing tells, read before longer writing |
| `samples/before-and-after.md` | six questions answered the padded way and the Terse way |
| `.claude-plugin/plugin.json` | the plugin manifest |
| `INSTALL.md`, `CREDITS.md`, `CHANGELOG.md`, `LICENSE` | install routes, credits, versions, licence |

## More for editors

Paid Claude Code skills from the same author:

- [Editor's Brain](https://adityavora.gumroad.com/l/editors-brain?utm_source=github&utm_medium=readme&utm_campaign=useu-q4): the planning half of editing, done to a method, from one script.
- [Session Board](https://adityavora.gumroad.com/l/session-board?utm_source=github&utm_medium=readme&utm_campaign=useu-q4): a paste-ready prompt for every session, on one board.
- [AE Script Builder](https://adityavora.gumroad.com/l/ae-script-builder?utm_source=github&utm_medium=readme&utm_campaign=useu-q4): scripted After Effects comps, checked before you press Run.
- [Chart Shorts Kit](https://adityavora.gumroad.com/l/chart-shorts-kit?utm_source=github&utm_medium=readme&utm_campaign=useu-q4): numbers in, a finished 38-second chart Short out. No After Effects.

Also free: [Session Board Lite](https://github.com/adityavora16/session-board-lite) splits one big
job into Claude Code sessions you can run in parallel.

## Licence

MIT, see [`LICENSE`](LICENSE). One exception: `skills/terse/references/ai-tells.md` and the list of
writing tells in the second half of `skills/terse/SKILL.md` are adapted from Wikipedia's "Signs of
AI writing" page and stay under CC BY-SA 4.0. Details in [`CREDITS.md`](CREDITS.md).

Terse is provided as is. Claude's replies vary; you are responsible for what you publish or act on.
