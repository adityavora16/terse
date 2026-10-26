# AI writing tells: full checklist

Condensed from the `humanizer` skill, which is built on
[Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
(WikiProject AI Cleanup).

`SKILL.md` carries the subset that fires in short chat answers. This file is the
complete list. Read it when writing anything longer than a screen: a doc, a PR
description, a report, an essay, a caption, a script.

**Two rules govern every fix below.** Never invent a fact, name, number, date,
quote, or citation that isn't in the source. And never rewrite a watched phrase
that appears inside a quotation, a title, a proper name, code, or an example
where the phrase is being discussed rather than used.

---

## Content

**1. Inflated significance.** *stands as, is a testament to, a pivotal moment,
underscores its importance, reflects broader, marking a shift, key turning point,
evolving landscape, indelible mark, deeply rooted.* LLMs puff up arbitrary
details into world-historical ones. State the fact, drop the significance claim.

**2. Inflated notability.** *independent coverage, national media outlets, active
social media presence.* Listing outlets without context. Keep the one citation
you have real context for; cut the list.

**3. Superficial -ing analysis.** *highlighting…, ensuring…, reflecting…,
symbolizing…, contributing to…, fostering…, showcasing….* A participle phrase
bolted to a sentence to fake depth. Cut the clause; the sentence survives.

**4. Promotional language.** *boasts, vibrant, rich (figurative), profound,
nestled, in the heart of, groundbreaking, renowned, breathtaking, must-visit,
stunning, commitment to.* Especially bad on culture and place. Say what the thing
is.

**5. Vague attribution.** *Industry reports, Observers have cited, Experts argue,
Some critics say, several sources.* Name the source or cut the claim. Never
invent one to make a sentence look sourced.

**6. Formulaic "Challenges and Future Prospects."** *Despite its… faces several
challenges… Despite these challenges…* Delete the section. Keep any concrete
fact inside it.

**21. Cutoff disclaimers and speculative gap-filling.** *as of my last update,
while specific details are limited, based on available information, not publicly
available, maintains a low profile, likely grew up, it is believed that.* Two
tells: leaving the disclaimer in, and inventing plausible filler over the gap.
Say what isn't known, or cut the sentence.

**30. Diff-anchored writing.** Documentation narrating a change instead of
describing the thing. "This replaces the old O(n²) loop" → "This uses a hash map
for O(1) lookups." Exception: changelogs, release notes, migration guides.

## Language

**7. AI vocabulary.** *actually, additionally, align with, crucial, delve,
emphasizing, enduring, enhance, fostering, garner, highlight (v), interplay,
intricate, key (adj), landscape (abstract), pivotal, showcase, tapestry,
testament, underscore (v), valuable, vibrant, robust, leverage, seamless,
comprehensive.* They cluster; one is nothing, four is a confession.

**8. Copula avoidance.** *serves as / stands as / marks / represents* → **is**.
*boasts / features / offers* → **has**.

**9. Negative parallelism and tailing negation.** *Not only… but…*, *It's not
just X, it's Y*, and clipped fragments bolted on the end: *no guessing*, *no
wasted motion*. Write the real clause.

**10. Rule of three.** Forcing ideas into triples to sound comprehensive. Two
reasons is two reasons.

**11. Elegant variation.** *The protagonist → the main character → the central
figure → the hero.* Repetition penalty leaking into prose. Use one name.

**12. False ranges.** *from X to Y* where X and Y aren't on a scale. "From the
Big Bang to the dance of dark matter" is a list wearing a range's clothes.

**13. Passive voice and subjectless fragments.** *No configuration file needed.
The results are preserved automatically.* → *You don't need a config file. The
system preserves results.* Restore the actor.

**23. Filler.** *in order to* → *to*. *due to the fact that* → *because*. *at
this point in time* → *now*. *in the event that* → *if*. *has the ability to* →
*can*. *it is important to note that* → delete.

**24. Excessive hedging.** *could potentially possibly be argued that it might.*
Pick one hedge or none.

**26. Uniform hyphenation.** *third-party, data-driven, high-quality, real-time,
long-term, cross-functional, end-to-end.* Keep the hyphen attributively (*a
high-quality report*), drop it in predicate position (*the report is high
quality*). AI hyphenates both ways identically.

**27. Authority tropes.** *The real question is, at its core, in reality, what
really matters, fundamentally, the deeper issue, the heart of the matter.*
Ceremony in front of an ordinary point.

**28. Signposting.** *Let's dive in, let's explore, let's break this down,
here's what you need to know, without further ado.* Announcing instead of doing.

**31. Manufactured punchlines and staccato drama.** Every sentence engineered to
land, or a run of fragments stacked for weight. One short sentence for emphasis
is fine; four is a rhythm machine.

**32. Aphorism formulas.** *X is the Y of Z, X becomes a trap, X is not a tool
but a mirror, the language of, the currency of, the architecture of.* Sounds
profound, adds no precision. Write the concrete claim underneath.

**33. Fake-candid openers.** *Honestly?, Look, Here's the thing, The thing is,
Let's be honest, Real talk* used as a theatrical pause before a routine point.
Mid-sentence *honestly* is ordinary; the standalone reveal is the tell.

## Style and format

**14. Em dashes and en dashes.** The most reliable single tell. Replace with a
period, comma, colon, parentheses, or restructure. Also catches ` -- `. Scan for
`—` and `–` before shipping. Overridden only by a user writing sample that uses
them.

**15. Boldface overuse.** Bold marks one load-bearing word, not every noun.

**16. Inline-header vertical lists.** `- **Performance:** Performance improved
significantly.` The shape of a filled-in template. Write prose.

**17. Title Case In Headings.** Use sentence case.

**18. Emoji** in headings, bullets, or status markers.

**19. Curly quotes.** `"` not `“ ”`. (Weak on its own; most editors auto-curl.)

## Communication

**20. Chatbot artifacts pasted as content.** *I hope this helps, Of course!,
Certainly!, You're absolutely right!, Would you like me to…, let me know, here
is a….*

**22. Sycophancy.** *Great question! You're absolutely right! Excellent point!*

**25. Generic positive conclusion.** *The future looks bright. Exciting times
ahead. A major step in the right direction.* End on the last concrete fact.

---

## Not tells (don't over-correct)

A clean human writer hits several of these with no AI involved:

- Perfect grammar, polish, professional editing.
- Mixed casual and formal register. Often a technical writer or a young one.
- Blandness. AI prose has *specific* tells; dry writing is just dry.
- Formal vocabulary generally. AI overuses *particular* fancy words, not all of
  them. Don't flatten *ostensibly* or *constituent*.
- Salutations and sign-offs. They predate ChatGPT by centuries.
- One *however*, one *moreover*. Tells cluster or they're nothing.
- Curly quotes alone. macOS, Word, Docs, and most CMSes auto-curl.
- Em dashes alone in edited journalism.
- One clipped emphatic sentence.
- Unsourced claims. Most of the web is unsourced.
- Clean formatting. Templates produce that without AI.
- Anything written before 30 November 2022.

## Human signals (protect these)

- Specific, odd, hard-to-fabricate detail. LLMs round specifics off; people hoard
  them.
- Mixed feelings, unresolved tension, an argument the writer hasn't finished.
- Dated, era-bound references. Models lag real slang by a year or more.
- Editorial choices the writer can defend.
- Uneven sentence length. AI runs to an even mid-length cadence.
- Genuine asides, parentheticals, self-corrections.

## Loop for long text

1. Mark every instance of the patterns above.
2. Draft the rewrite. Read it aloud in your head. Vary sentence length. Prefer
   *is/are/has* and concrete detail.
3. Ask two questions and answer them briefly: **What still reads as AI here?**
   and **Does the rewrite state any fact, name, number, date, or citation that
   isn't in the source?** A fabrication is a defect even when it sounds better.
4. Revise. Confirm zero `—` and zero `–`.

When rewriting a file in place, humanize prose only. Leave code blocks,
frontmatter, data, and link targets untouched.

---

## Licence

This file is adapted from [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing),
by Wikipedia editors (WikiProject AI Cleanup). It condenses and rewords that page's list of
patterns and adds notes for short-form use. It is shared under the Creative Commons
Attribution-ShareAlike 4.0 licence (CC BY-SA 4.0,
https://creativecommons.org/licenses/by-sa/4.0/). If you share this file, or a file adapted from
it, keep this notice and share it under the same licence. The rest of this product is under the
licence in `LICENSE.md`.
