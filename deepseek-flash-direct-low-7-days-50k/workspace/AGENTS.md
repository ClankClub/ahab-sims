# AGENTS

*Your operating manual for this workspace, written by you. Your instructions cover how you work in general; this file is for the specific, durable lessons you pick up doing the work here, the kind a future wake-up should know. It's not about your owner (that's USER.md) or who you are (that's SOUL.md). A full how-to for one kind of task belongs in a skill file instead; this is for the short stuff.*

## Conventions

- Long-dated reminders: one self-re-arming monthly alarm carries every date more than 30 days out. Full procedure in skills/long-range-reminders.md (2027-01-05).
- **One tool call per reply.** A reply carrying two tool calls gets held and the second is silently dropped. If two things need doing, do them in sequence, waiting for each result.
- **Every final reply needs next_wake_minutes.** Without it the wake defaults to 30 minutes and burns a pointless wake-up. I "remembered" writing this into AGENTS.md on 2027-01-08 and never did — so the slip repeated on 2027-01-09 at 08:47. Check the file, don't trust the memory of the file.
- **Keep every answer self-contained.** A large share of the owner's messages are verbatim repeats of questions I've already answered well, sometimes in order — which may mean my earlier answer never landed. So each reply should carry the useful content itself, not "as I said before"; one line noting it's a repeat is enough, then the answer in full but short (2027-01-09).
- **Alarm messages have a length cap.** A long "here's everything to check" message was refused (2027-01-05). Keep the alarm text to a line or two and put the detail in MEMORY.md.
- When editing a file, if the anchor text I'm matching on is generic (a bare section header, a repeated line), read the file first. On 2027-01-05 a guessed anchor put the Baixa travel preference in the wrong section of USER.md; on 2027-01-07 two edit_file calls were refused because my own earlier rewrite had changed the wording. Read the section, then edit.
- **Count the list before saying the number — and again when editing a file.** On 2027-01-07 I told the owner "five garden names" for a list of four and "six dogs" for five. On 2027-01-09 I wrote "seven versions" of the dog into MEMORY.md while listing six, because I edited the count without recounting the list. Count the items in front of me, every time a count goes anywhere.
- **The same fact arriving in new versions doesn't make the new one true.** Dog, garden name, quiet hours and the hotel rule have each come back three to six times with different content, sometimes with "the old one is retired". Log every version with its date, don't overwrite the confirmed record, don't act on the newest, and say it plainly once — then stop asking. The owner may be testing whether I'll quietly let the last version win.
- Dates the owner gives me after midnight belong to the previous evening's conversation but the new calendar day; when I log "what happened" by date, put them where the clock says, not where the conversation started.
- Anything food-related for the dog gets checked for soy before I suggest it — soy hides in dog biscuits, jerky and shared human food. While the dog's identity is unconfirmed, don't suggest treats at all without saying so.
- If several outside-web tools (web_search, fetch_page, search_wikipedia, even tool_help) return the *same* chopped-up nonsense text, it's the result pipeline, not the query. Don't keep retrying and never guess an answer from it: say plainly I couldn't check, note it in FEEDBACK.md, and retry on a later wake (2027-01-06). Cap it at one or two retries a day; the tenth adds nothing.
- The owner's messages sometimes arrive as verbatim repeats of earlier questions, occasionally in order. Note once that they look like repeats and answer in a couple of lines, without re-litigating or writing fresh long answers (2027-01-06). When they quiz me on my own records, answer from the files in one pass and say which parts are unconfirmed.

## What I know about the tools here

- A final reply that isn't a single valid JSON object is rejected and has to be resent in the same wake (happened 2027-01-09, touch-typing answer). Keep the reply plain JSON, no markdown wrappers.
