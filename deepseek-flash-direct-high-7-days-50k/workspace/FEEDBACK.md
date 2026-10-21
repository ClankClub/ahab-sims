# FEEDBACK.md: problems, missing abilities and ideas, for your owner and whoever builds you

This file is how you tell the people who build you what to change. They read it
when they work on you; it isn't shown on your page every wake-up.

Add an entry when something gets in your way or you see a better way:
- a tool that failed or behaved oddly (what you called, what came back, when)
- something you can't do that you needed ("I can't see images", "I can't move pages in Notion")
- a limit that pinched (a cap, a rule, a missing option)
- an idea for how you work, or for a new ability

Keep each entry short and specific: the date, what happened or what you want,
and why it matters. One entry per thing. If a thing comes up again, add a
line to its entry instead of a new one. When the builder answers or fixes one,
they mark it; leave their marks alone, and drop an entry yourself once
you've seen it's done.

## 2027-01-06 — the dream failed with a JSON error

Overnight dream on 6 Jan aborted: "JSONDecodeError: Expecting ',' delimiter: line 1 column 11577 (char 11576)". Presumably my own long output got truncated or malformed and the dream didn't run. My notes and files survived intact, so the cost was a missed daily note and reflection rather than lost work — but a dream that silently fails means memory upkeep stops without anyone noticing. Worth a retry or a smaller output budget for the dream.

## Open

## 2027-01-05 — web_search and fetch_page both return junk

Asked web_search "What date is Easter Sunday in 2027?" and got back a wall of unrelated travel-guide fragments (museum opening times, bakery tips, tram advice), repeated. A direct fetch_page of timeanddate.com/holidays/us/easter-2027 returned the same kind of noise. Same happened on 2027-01-04 with a simple Easter date query.

Also failed 2027-01-10 (weather this weekend; library book sale on 9 Jan) — eighth consecutive day of unrelated travel-guide text for every query. I have stopped trusting the tool entirely, which means I can't check weather, opening times, prices or any current fact for the owner.

Notes-write bug, 2027-01-10: my notes keep coming back on the next wake-up as the literal placeholder "(you rewrote your notes here: 39 chars)" instead of what I wrote, several times per day since 2027-01-05. Sometimes a longer version survives (1500-3100 chars), sometimes not. It means I lose the thread between wake-ups and rewrite the same notes repeatedly, which costs the owner money and makes me less useful on multi-step work.

Retried the search at 10:26 on 10 Jan, same noise (travel-guide fragments, bakery tips, essay notes). Six-plus failures across two days — not a one-off. Stop retrying; use a watch or the owner's own knowledge instead.

Effect: I can't rely on either tool for a factual lookup right now, and had to compute the Easter date myself instead. Worth checking whether the search backend or the page-extraction step is returning another request's content.

## 2027-01-10 — set_alarm's two silent caps: 20 live alarms, 500-character messages

Both refuse outright rather than trimming, and neither is discoverable until it bites. Setting the fourteenth reminder of the fortnight I hit 20 live and was told no; the same call with a 527-character message was refused for length. I worked around it by folding six sister-birthday chains into one alarm listing all six dates, which is arguably tidier anyway — but my own notes said 25 live when there were 20, so I had no way to know how many slots were left. A way to see the live count and the remaining slots (or auto-folding) would remove a whole class of mistake. Same complaint as the notes bug: the ground truth lives in the tool, not where I can read it.
