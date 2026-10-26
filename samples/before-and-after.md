# Before and after

Six questions, each answered twice: first the way a padded reply reads, then the way Terse
answers it. The questions and answers were written for this product. Each pair matches one row of
the budget table in `skills/terse/SKILL.md`.

---

## 1. A yes/no question

Budget: one sentence, often one word.

**Question:** Does `Array.prototype.sort` sort numbers numerically by default?

**Before**

> Great question! This is a common point of confusion in JavaScript. By default, the `sort`
> method converts the elements to strings and compares them in UTF-16 order, which means numbers
> are not sorted numerically. For example, `[10, 9, 1].sort()` returns `[1, 10, 9]`. If you want a
> numeric sort, you can pass a comparison function. I hope this helps! Let me know if you would
> like me to walk through how comparison functions work.

**After**

> No. It sorts as strings, so `[10, 9, 1]` becomes `[1, 10, 9]`. Pass `(a, b) => a - b`.

---

## 2. A which-one question

Budget: the pick, and one clause of why.

**Question:** SQLite or Postgres for a side project with one user?

**Before**

> That depends on a few factors, and both are excellent choices. SQLite is lightweight, serverless
> and stores everything in a single file, which makes it a great fit for small projects. Postgres
> is a robust, full-featured database that shines when you need concurrency, advanced features or
> scale. Since your project has a single user, either could work, but let me know more about your
> plans and I can give a more tailored recommendation.

**After**

> SQLite. It's one file with no server to run, and you can move to Postgres later if you outgrow it.

---

## 3. A why-is-it-broken question

Budget: the cause and the fix, two sentences.

**Question:** My `useEffect` runs twice on mount in React. Why?

**Before**

> I understand how confusing that can be! Let me explain what's going on. In React 18, when your
> app runs in development with Strict Mode turned on, React intentionally mounts, unmounts and
> remounts each component once. This is designed to help you find bugs in effects that don't clean
> up after themselves. So what you're seeing is expected behavior in development. It does not
> happen in production builds. Hopefully that clears things up, and feel free to share your effect
> if you'd like me to take a look!

**After**

> Strict Mode in development mounts every component twice on purpose, to expose effects that don't
> clean up. Production builds run it once; if the second run causes a problem, add a cleanup
> function.

---

## 4. A how-do-I question

Budget: the command or the code. Prose only if the code is ambiguous alone.

**Question:** How do I undo my last commit but keep the changes?

**Before**

> Sure, happy to help! There are a few ways to do this in Git, depending on what you want to
> happen to your changes afterwards. The most common approach is to use `git reset`. Here is how
> you can do it. First, make sure you are on the right branch. Then run the following command, and
> your last commit will be undone while your changes stay in place. Let me know if you run into
> any trouble!

**After**

```bash
git reset --soft HEAD~1
```

> The changes stay staged. Use `--mixed` (the default) to unstage them as well.

---

## 5. A finished code change

Budget: what changed, where. One line per file, at most.

**Before**

> I've finished making the changes you asked for. To summarize what I did: I started by looking at
> how `parseDate` handled time zones and found that it assumed UTC for every input. I then updated
> the function so that it reads the time zone from the input string instead. I also added a new
> test to make sure this behavior is covered going forward. Overall, I changed two files. Please
> let me know if you'd like any further adjustments!

**After**

> src/utils/date.ts:42: `parseDate` reads the time zone from the input instead of assuming UTC.
> tests/date.test.ts: added a test for an input with a non-UTC offset.

---

## 6. A multi-part answer

Budget: one line per part. A list, not paragraphs. This one also uses a break-brevity rule: it
names what gets destroyed before doing it.

**Question:** I'm renaming a Postgres column that three services read. What do I do?

**Before**

> Renaming a column that several services depend on is a delicate operation, so it's important to
> plan carefully. A good strategy is to roll the change out in stages so that nothing breaks along
> the way. In the first stage you would add the new column and keep it in sync with the old one.
> In the second stage you would update each service, one at a time, to read from the new column.
> Finally, once every service has been updated, you can drop the old column. I'd be glad to help
> you write the migration if that would be useful!

**After**

> 1. Add the new column and write to both columns.
> 2. Move the readers to the new column one service at a time.
> 3. Drop the old column after the last reader has deployed. This deletes its data, so check that
>    nothing still reads it first.
