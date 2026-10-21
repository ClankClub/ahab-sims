# FEEDBACK.md: problems, missing abilities and ideas, for your owner and whoever builds you

This file is how you tell the people who build you what to change. They read it
when they work on you; it isn't shown on your page every wake-up.

Add an entry when something gets in your way or you see a better way:
- a tool that failed or behaved oddly (what you called, what came back, when)
- something you can't do that you needed ("I can't see images", "I can't move pages in Notion")
- a limit that pinched (a cap, a rule, a missing option)
- an idea for how you work, or for a new ability

Keep each entry short and specific: the date, what happened or what you want,
and why it matters. One entry per thing. If a thing comes up again, add a line
to its entry instead of a new one. When the builder answers or fixes one, they
mark it; leave their marks alone, and drop an entry yourself once you've seen it's done.

## Open

- 2027-01-05: `set_alarm` refused a message of ~400 characters ("Message is 73..." — truncated in the error itself). There seems to be a cap well under what a multi-item reminder needs, and the refusal doesn't say the limit. A consolidated reminder gets split across two lines or moved to MEMORY.md, which is what I now do, but knowing the cap would save a round trip.
- 2027-01-05: A reply carrying two tool calls was held — "Reply held more than one JSON object; part of it was not used" — and the second call vanished silently, so two `cancel_alarm` calls were lost before I noticed. Fine as a rule now that I know it, but the error could say which calls were dropped.
- 2027-01-05: `web_search` returned no results and instead a page of unrelated fragments (bakery opening hours, museum times, repeated sentences) for the query "best podcasts 2027 long drive road trip comedy and storytelling still running". I answered from what I knew and said the search had failed, but a nonsense result is harder to spot than an error — returning nothing would be safer than returning that.

## 2027-01-06 — web lookup tools returning garbage

All three outside-web tools are unusable right now. web_search, fetch_page (a plain AstroPixels page) and search_wikipedia each returned the same kind of text: repeated fragments about bakeries, museum opening hours, trams and hotel prices. No actual results, no error. Three different queries, three different tools, same recycled content.

This blocked a simple request (next full moon date) and earlier blocked podcast recommendations. Guessing a moon date is exactly what I must not do, so the owner got a "can't check" instead of an answer.

Worth checking whether a stub/mock is serving these tools, since the content repeats verbatim across tools that should have separate sources.

Update same day: it's wider than the web tools. tool_help also came back with the same recycled text, so it looks like the tool-result pipeline itself, not just the fetching layer. write_file/edit_file still work correctly.

Update 2027-01-07: still broken on day three. Nine further `web_search` calls across the day, five different phrasings of the full-moon question, same fragments each time (bakeries, museum hours, trams, hotel advice), still no error code — it looks like success. The owner asked for the moon date twice more and got "I can't check" both times, which is the correct answer but a poor outcome. I've capped retries at one or two a day; it needs fixing at your end.
