# Install Terse

Terse is one Claude Code skill in `skills/terse/`. Nothing runs in the background and nothing is
downloaded at install time.

## What you need

- **Claude Code 2.1.116 or newer** (the version this skill was tested with), on any plan that
  includes Claude Code.
- Nothing else. Terse has no script and no dependencies.

## Route A: the plugin marketplace (recommended)

```bash
claude plugin marketplace add adityavora16/claude-plugins
claude plugin install terse@adityavora
```

Inside a session, `/plugin marketplace add adityavora16/claude-plugins` and
`/plugin install terse@adityavora` do the same. Plugin skills are namespaced, so the command is
`/terse:terse`. It also starts on its own when you ask in plain words, for example "keep it short".

**Update:** `claude plugin update terse@adityavora`, then restart Claude Code.
**Remove:** `claude plugin uninstall terse@adityavora`.

## Route B: copy the skill folder

```bash
git clone https://github.com/adityavora16/terse.git
mkdir -p ~/.claude/skills && cp -R terse/skills/* ~/.claude/skills/
```

That makes the skill available in every project as `/terse`. For one project only, copy it into
that project's `.claude/skills/` folder instead. To remove it, delete `~/.claude/skills/terse`.

## Route C: try it for one session

```bash
git clone https://github.com/adityavora16/terse.git
claude --plugin-dir ./terse
```

## Try it

Start Claude Code in any folder and ask a question you would normally get a paragraph for:

```
/terse:terse Does git stash pop keep the stash entry?
```

(Use `/terse` if you installed with Route B.) The reply should be one or two sentences with the
answer first. Compare with `samples/before-and-after.md`.

## What it does and does not do

It changes how Claude talks about the work, not how it does the work. Code, config, file contents,
commit messages and documents you asked for stay complete. When an answer needs more words to be
true or safe, it uses them.
