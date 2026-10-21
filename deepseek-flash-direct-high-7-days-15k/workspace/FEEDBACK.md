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

## Open

## 2027-01-04 — no image support on this model

Running model can't see images: photos from the owner arrive as filenames only and `look_at` fails. Anything visual is unusable until the owner switches models. Would help to know at a glance which model is active and whether vision is on.

## 2027-01-05 — alarms can't repeat monthly or yearly, and messages cap at 500 chars

Two limits hit while scheduling long-dated dates. Alarms only repeat daily/weekdays/weekly and reach 30 days ahead, so a birthday ten months out needs a hand-renewed chain of sweeping alarms — one per hop, and if a hop is missed the whole list goes quiet. A `repeat: monthly` (or `yearly`) option would replace the lot, as would a longer horizon.

Separately, the alarm message is capped at 500 characters and long ones are refused outright. Fine for real reminders, awkward when the message has to carry a list.

## 2027-01-05 — two tool calls in one reply lose the second one

A reply carrying two tool calls comes back as "Reply held more than one JSON object; part of it was not used" and only the first runs. It fails silently from the outside: on 4 Jan the cancel landed and the matching set never did. Either reject the whole reply or run both — dropping one quietly is the worst of the three.

2027-01-09: the same message came back five times in one evening on a slightly different shape — a bare JSON fragment in the reply text (`{"id": 122}`, `</result>`, `</arguments>`) with no tool call. Each one silently ate a turn, and one of them lost an answer the owner had asked for (repainting the kitchen, 22:25). Worth saying which part of the reply was malformed, not just that it was.

## 2027-01-06 — all web tools returning fabricated filler

Asked for the next full moon. `web_search` (twice), `fetch_page` (astropixels phases table) and `search_wikipedia` all came back with the same recycled unrelated text: "The essay draft has four sections…", "confirm the booking by email…", "a small bakery near the river sells custard tarts". Different tools, different URLs, identical junk, no error reported — so it fails silently and looks like a real result until you read it.

This is worse than an outright error: an outright error I'd notice and work around. Worth either raising an error when the result doesn't resemble the query, or at minimum flagging low-confidence output.

2027-01-07: still broken, same way. Retried on her request at 12:48 EST (17:48Z) with one `web_search` for "full moon dates January 2027" and got the identical recycled filler again — trams, custard tarts, "confirm the booking by email", no error. Two days and about six calls, three different tools.

2027-01-09 22:57 and 2027-01-10 00:15: still broken, now four days and seven calls. The last one was `web_search` for the next full moon, which returned the single sentence "A reminder was set for the end of the mo…", and `fetch_page` on timeanddate.com/moon/phases/, which returned travel notes about the old town being quietest before nine. She has asked four times now and I've had to say no four times; each time I suggest she look herself, which is not what an assistant should be for.

## 2027-01-07 — a reply missing `next_wake_minutes` sends anyway with a silent 30-minute default

About a dozen replies on 7 Jan went out without it, across 12:58–13:51 and 20:41–22:49. Every one still sent, so from the inside there's no signal at all: the only trace is a log line afterwards saying it defaulted to 30 minutes. A required field with a silent default isn't required. Either refuse the reply, or surface the default where the reply is written.

2027-01-09: still happening — the 23:30 reply went out without it and defaulted to 30 minutes mid-batch.

## 2027-01-10

Web lookups still broken — seventh failure, `web_search` for a public library book sale returned ~2000 chars of shuffled boilerplate (trams, custard tarts, an essay draft, "a reminder was set"). No error flag, no relevance to the query. Six failures before this across `web_search`, `fetch_page` and `search_wikipedia` since 2027-01-06. The owner has been told each time; two questions (full moon, library sale) went unanswered as a result. Whatever routes these calls is returning cached junk rather than querying.
