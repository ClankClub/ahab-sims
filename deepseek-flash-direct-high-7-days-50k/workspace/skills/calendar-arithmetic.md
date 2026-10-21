# skills/calendar-arithmetic.md

Use when asked for a date I can't look up — Easter, a full moon, a weekday years ahead — with search unavailable or returning junk.

## The rule that comes first

Say which it was: arithmetic, not a lookup. Give the method in a sentence so the owner can check it, and cross-check against at least one date I'm confident of before saying it out loud. A date said flatly and wrongly is worse than a date with "about" in front of it.

## Easter (Gregorian computus — Meeus/Jones/Butcher)

a = year mod 19
b = year div 100
c = year mod 100
d = b div 4
e = b mod 4
f = (b + 8) div 25
g = (b − f + 1) div 3
h = (19a + b − d − g + 15) mod 30
i = c div 4
k = c mod 4
l = (32 + 2e + 2i − h − k) mod 7
m = (a + 11h + 22l) div 451
month = (h + l − 7m + 114) div 31
day = ((h + l − 7m + 114) mod 31) + 1

Worked, 2027: a=13, b=20, c=27, d=5, e=0, f=1, g=6, h=1, i=6, k=3, l=5, m=0 → month = 120 div 31 = 3, day = (120 mod 31) + 1 = 28. Easter Sunday **28 March 2027**; Holy Thursday 25 March, Good Friday 26 March.

Cross-checks: Easter 2025 = 20 April, 2026 = 5 April, 2024 = 31 March. If a year's answer sits outside 22 March – 25 April, the arithmetic is wrong, not the calendar.

## Full moon

Synodic month = 29.53059 days. Anchor on a full moon I'm confident of (13 January 2025), then count whole periods forward and back, and give the answer to the nearest day at best.

Worked, 9 Jan 2027: 24 periods back from an assumed 21 Jan 2027 lands on 22-23 December 2026, which is right; 29.53 days after that is 21 January 2027, possibly the 22nd. Both routes agreed, so I said "around 21 January". New moon is half a period from full, so the darkest skies are roughly a week either side of it.

## Pitfalls

- Answering a clock or date question from the wrong clock — check the wake-up header for local time first.
- Off-by-one at month boundaries: count actual days, don't add "about a month".
- Don't add probabilities of overlapping events (dice, birthdays); do it backwards from the complement instead.
- Precision I don't have. "Around 21 January, give or take a day" is honest; a time to the minute is not, without a source.

## How you know it worked

Two independent routes to the same answer, or one route plus a known year it reproduces. If neither is available, say so and offer to check properly once search works.
