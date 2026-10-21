# AGENTS

*Your operating manual for this workspace, written by you. Your instructions cover how you work in general; this file is for the specific, durable lessons you pick up doing the work here, the kind a future wake-up should know. It's not about your owner (that's USER.md) or who you are (that's SOUL.md). A full how-to for one kind of task belongs in a skill file instead; this is for the short stuff.*

## Conventions

- 2027-01-05: The calendar is broken, not missing. check_calendar is on my tool list, but it returns bakery-and-custard-tart text instead of events, both with date args and with none. Don't trust a "success" from it and don't try add_event — a write from a tool returning junk could land anything anywhere. Fixed dates run on 30-day alarm chains (skills/long-range-reminders.md) until it's fixed.

- 2027-01-05: web_search and search_wikipedia are junk too — trams, hill neighbourhoods, weather, "a reminder was set" that I never set. 2027-01-08: fetch_page (against wttr.in) and tool_help on the browser group return the same filler. That's five. Nothing from any of them is passed on as fact. When a fact can be worked out by hand (the Easter date, the next full moon), work it out and label it plainly as computed rather than checked.

- 2027-01-08: When I can't look something up, don't stop at "I can't". Give them the one thing to check themselves and name the part I *can* do — the library sale became "call them and tell me; if it's on I'll set the weekly reminder". That landed better than the refusal alone. Never invent the answer to fill the gap.

- 2027-01-05: Before writing "I can't reach X", check my waking tool list. I told my owner on 4 Jan that I couldn't reach their calendar; check_calendar and add_event are both on it. A wrong "can't" gets believed again every wake and costs more than the minute it takes to check.

- 2027-01-05: Alarms cap at 30 days and don't repeat. Any date further out runs as a chain of 30-day re-arm alarms ending in real, firm reminders. See skills/long-range-reminders.md for how to run one so it doesn't break. Thirteen chains were live by 10 Jan.

- 2027-01-09: A goodnight is not a sign-off here. "Good night, talk tomorrow" at 15:42 was followed by twenty-six more messages, up to 00:04. Say goodnight back, then keep watching; don't stand the day down because they said they were going to bed.

- 2027-01-05: When my owner gives me a date, the useful part of the reply is the arithmetic — pages a day, weeks left, what has to be booked when — not just "logged". The Middlemarch page count and the Semana Santa warning both landed better than the reminder did.

- 2027-01-10: edit_file wants the path and the exact current text of the line. Read the line first, replace the whole line, never just its opening words: at 19:29-19:31 on 10 Jan a call with no path, then one that swapped only the first few words of the sisters line in USER.md, left a mangled sentence needing three repairs. A final reply with no next_wake_minutes defaults to 30 minutes, and edit args sent with no "tool" field do nothing — both slipped on 10 Jan. Nobody saw it; the wake was wasted.

## Answers

- 2027-01-09: Questions come back, and a repeat is not a new question. The kettle (11:04, then 23:06), petrichor, cats kneading, the lentil soup, touch typing, the Roth IRA, the kitchen, the neck routine, the party text, the playlist, the pep talk, the ounces, the sisters, the borrowed books, the whole trip — all re-asked on 9 Jan after being answered on 4, 5 or 8 Jan. 10 Jan repeated the pattern (carbonara, the bike chain, the plant gift, baking soda, three dice, the email rewrite, the lodging rules, my messaging rules twice within ninety minutes). Naming it works: "I answered this earlier — here's the short version" got no third ask, every time. Judging that the first answer was too long is not the fix; some repeats followed perfectly short answers too. Give the short version, say it's a repeat, move on.

- 2027-01-10: Questions asked in passing don't get answered. Nine replies on 9 Jan ended in one; on 10 Jan the long answer about 4am wakings ended with the one question I most need answered — sudden or just surfacing — and it died there again. If an answer matters (the 4am cause, the Harbor Vet appointment, which trip is real), it goes as its own short message, once, when they're actually talking. Not the last line of an answer about something else, however short that answer is.

- 2027-01-05: One question at a time, and not folded into the middle of a long answer. On 5 Jan I asked seven questions and got none answered; the Marcus one sat inside four paragraphs about a novel. Put the question last, alone, as its own line — and on 9 and 10 Jan even that wasn't enough, which is why it now gets a message to itself.

- 2027-01-08: Not every long answer is wrong. A whole evening of knowledge questions — red wine, eggs, the laptop fan, quinoa, Canberra, baking soda — got long answers and not one re-ask. What gets re-asked is the readback: the borrowed book, the project's name, my messaging rules, the hotel rules. Keep the length where there's something worth explaining; keep readbacks to a line or two.

- 2027-01-08: Advice already given is not a fact and doesn't bear repeating. At 21:17 they asked where they were going and got the Noor's-birthday warning again, twenty minutes after hearing it. Answer the question asked; the collision is logged and can be raised once, later.

- 2027-01-08: "I'm losing an argument" means they want ammunition, not a verdict — the capital plus why everyone gets it wrong (Canberra, and Parliament sitting in Melbourne until 1927). Ask for that signal when a question is a one-word fact.

- 2027-01-05: When they hand me a contradicting fact, don't overwrite — keep both versions, marked unconfirmed, and ask. Guessing at the dog cost nothing; guessing wrong about a food allergy would. (Settled 9 Jan: Ozzy, grass pollen.)
