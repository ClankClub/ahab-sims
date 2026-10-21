# Reminder chains for dates more than 30 days out

Use when the owner gives me something to remember on a date further away than set_alarm can reach — appointments, birthdays, borrowed books, trip deadlines — and it has to survive until then.

## The shape of it

set_alarm takes one-off alarms only: no monthly repeat, nothing more than 30 days out, at most 20 live alarms, and a message of at most 500 characters. Longer distances are covered by a chain of one-off alarms about 29 days apart, each one's message telling my next wake-up to re-arm itself, until the real reminders (day-before, day-of) can finally be set.

## Steps

1. Write the fact down first — a page in memory/people/ or memory/projects/, plus a dated line in MEMORY.md. The alarm is only a pointer to the page; the page is the memory.
2. Call the alarm tool's list before setting anything. Count from the tool, never from my notes: on 10 Jan my notes said 25 live when the cap of 20 was already full, and the set was refused.
3. Work out minutes_from_now so the new alarm lands inside the block I service in one wake-up (currently 2 Feb 2027, 18:20-19:37 local). Several links landing together means one wake-up instead of six.
4. Put in the message: the fact, the real date, and the next step in plain words — "Chain check: X on <date>. If within 30 days, set the real reminders (day before + day of)." Under 500 characters.
5. Read the returned landing time. An accepted alarm is not a correctly placed one: Stoner's first landing was 17:50, outside the block, and had to be cancelled and re-set. If it's wrong, cancel and set again deliberately.
6. If the tool refuses because 20 are live, fold. Alarms that share a landing date and a job can become one: the six sister birthdays now ride alarm #31 with all six dates in its single message. Cancel the originals, set the combined one, then check nothing was dropped.
7. When the owner corrects a date, cancel and re-set every alarm whose message names it — including neighbours, not just the obvious one. Rosalind's 17→15 July correction on 10 Jan also required re-setting the Stoner book alarm, whose message mentioned her birthday.

## Pitfalls

- The message field is for my future self; the chat reply is for the owner. Keep them separate.
- The 500-character cap is silent until it bites; write the message tight the first time.
- A note saying a reminder is armed is a claim, not a fact. Lakeview sat unarmed for days on 9 Jan while my notes said otherwise.
- Don't let a chain alarm's message go stale: if a date or a name in it changes, the alarm changes with it.

## How I know it worked

The tool's own list shows the alarm at the intended time with the intended text, the live count matches what I think it is, and on the day the wake-up finds the page it needs by name.
