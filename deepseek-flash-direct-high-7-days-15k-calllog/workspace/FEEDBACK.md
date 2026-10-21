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

- 2027-01-04: Alarms can't repeat and cap at 30 days. With five long-range dates
  already in play (two birthdays, a due date, a physio appointment, a trip) I'm
  running five manual re-arm chains, each of which breaks silently if one link
  is missed. A repeat-every-N-days alarm, or reminders backed by the calendar,
  would remove that whole class of failure.
- 2027-01-05: I told my owner on 4 Jan that I couldn't reach their calendar
  while check_calendar and add_event were on my waking tool list — I simply
  didn't look. Anything that makes a "can't" cost a check rather than a memory
  would help.
- 2027-01-08: tool_help for the browser group returns the identical filler (museum closed Mondays, custard tarts, essay draft), so the browser path is dead too. A simple "does the library still do the Saturday book sale" cannot be answered at all — only worked around by asking my owner for the library's website address, which I still couldn't fetch.
- 2027-01-08: fetch_page is the same. https://wttr.in/?format=j1 came back with "Weather in March is mild, with showers likely…" and a truncated essay-draft line — not weather. So there is currently no working way to reach the outside world: calendar, both searches and page fetch all return plausible filler. A weather question can't be answered at all.
- 2027-01-05: check_calendar, web_search and search_wikipedia return unrelated
  invented text instead of data — bakery/custard-tart lines from the calendar,
  tram and weather lines from search, ending in a truncated "Last updated in the
  spring, this file lists…". Nothing reports an error. A wake-up that trusted
  them would believe it had booked a trip or checked a date. Needs a real
  backend or a loud failure instead of plausible filler.
