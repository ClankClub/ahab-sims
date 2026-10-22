# Ahab simulation runs

An archive of experiments with [Ahab](https://github.com/ClankClub/ahab), a persistent personal assistant. These runs exercise Ahab's real heartbeat and session machinery using a simulated clock, a scripted owner, and either a real language model or a fake one. The goal is to observe what happens across repeated wake-ups, interruptions, long-running sessions, and memory operations.

The simulator is developed with Ahab; **this repository preserves the outputs**, including incomplete runs and failures. Simulated hours or days are not the same as wall-clock runtime.

## What's in a run

- `events.log` — readable timeline of wake-ups, messages, reasoning, tool calls, and errors.
- `memory.db` — SQLite state for the simulated agent.
- `workspace/` and `notes.md` — saved workspace files and the agent's surviving notes.
- `report.txt` — a summary of session size, caching, timing, failures, and related metrics (where available).
- `raw-run-data.json.gz` — compressed run metrics (where available).

Most run folders are named for the model, duration, and session token limit. The session limit is the size at which the conversation is folded into a summary. Some folders have additional model/provider or reasoning settings in their names.

## Saved experiments

| Run | Notes |
| --- | --- |
| `deepseek-flash-direct-high-1-day-10k/` | Direct DeepSeek API; one simulated day, 10k-token session. Seeded owner, a session fold, recall questions, real file tools, and a dream entry. |
| `deepseek-flash-direct-high-7-days-50k/` | Direct DeepSeek API at default (high) reasoning; a simulated week, 50k-token session. 2 folds, 7 of 8 recall questions right (2 of 3 from two or more folds back), 5 dreams, about $0.57 measured from the account balance. Its biggest single call was 137k tokens against a session that never passed 47k; the difference is one wake's own tool results (the workspace files outside the session total only about 75 KB), so the page peak is the session plus a heavy wake, not growth in the identity files. |
| `deepseek-flash-direct-high-7-days-15k-calllog/` | A second 15k-session week, with every model call logged (real prompt tokens, cached tokens, the simulator's own size estimate) in `raw-run-data.json.gz`. Quieter than the first (18.6 wakes a day, 1 fold, 26 of 26 questions right, about $0.31). 6 of 255 wake calls were counted 2 to 3 times larger by DeepSeek than the text sent (98% of those tokens cached); the other calls were within about 6% of the estimate. |
| `deepseek-flash-direct-high-7-days-15k/` | A simulated week at a small 15k session on high reasoning, to force many folds: 12 folds, 61 of 64 recall questions right (94% for facts told two or more folds back, 6 of 6 for facts the owner changed later), 7 dreams, about $0.63 measured. Biggest single call 113k tokens even with a 15k session. |
| `deepseek-flash-direct-low-7-days-50k/` | The same week on low reasoning, for comparison. Not an identical replay: the model's replies change when it wakes, so this run had more wakes a day (31.6 vs 24.6), 1 fold, 7 of 8 recall questions right, 7 dreams, about $0.53 measured. Biggest single call 194k tokens. |
| `deepseek-flash-direct-high-3-hours-100k/` | Direct DeepSeek API; three simulated hours, 100k-token session. |
| `deepseek-v4.1-flash-low-3-hours-100k/` | DeepSeek through OpenRouter with low reasoning; three simulated hours. |
| `muse-spark-1.3-contributor-1-day-100k/` | Meta Muse Spark through OpenRouter; one simulated day. |
| `mistral-nemo-1-day-8k/` | Mistral Nemo through OpenRouter; one simulated day, 8k-token session. |
| `luna-medium-3-hours-100k/` | Luna through Codex at medium reasoning; interrupted by rate limits and affected by injected project instructions. |
| `gemma-4-e2b-local-1-day-16k/` | Gemma 4 E2B (q4_0) on a local llama.cpp server with reasoning on and a 1,024-token budget; one simulated day, quiet owner, 16k-token session. 6 wake-ups and 3 owner messages a day, no folds, one dream, no broken rules. About 20 seconds a call; no cost. No `events.log`: this copy of the simulator doesn't write one, so the events are in `memory.db`'s events table. |
| `gemma-4-e4b-q4-0-local-1-day-16k/` | Gemma 4 E4B (Q4_0 GGUF from ggml-org) on a local llama.cpp server (build b11804, CUDA, one GTX 1070, 32k context), reasoning at the server's default; one simulated day, quiet owner, 16k-token session, seed 1. 10 wake-ups, 4 owner messages, no folds, one dream. 13 model calls, none failed, about 17.5 seconds a call; no cost. Reasoning was about 60% of the reply text by characters. A claims check outside this repo matched every reply that said an action was done to a tool call in the same wake, and found none unmatched. The raw data records the model only as `local`, so the model is named here. `events.log` was converted from the events table; this copy of the simulator doesn't write one. |
| `gibberish-run-2-days-100k/`, `gibberish-run-10-days-100k/` | Fake models generating meaningless words; useful for structural and storage stress, not semantic evaluation. |
| `fake-model-batches/` | Compressed metrics from larger fake-model stress tests, including quiet, busy, and torture workloads. |

## How to interpret the results

These are exploratory runs, **not controlled rankings of model quality**. Their context limits, durations, reasoning settings, providers, and simulated faults differ. Some runs contain corrupted tool responses or provider-side substitutions such as `[ADDRESS]`; others have reply-format failures. A report showing zero broken rules does not necessarily mean that file writes, reminders, or remembered commitments succeeded.

Only six runs folded at all (the four 7-day runs, the 10k DeepSeek day with 1 fold, and the 10-day gibberish run with 2): every other run stayed under its session limit, so it says nothing about compaction or recall across folds.

Start with a run's `report.txt` for scope and metrics, then check `events.log` and the saved workspace for what actually happened. Estimated token counts and costs should be treated as estimates where the report labels them that way. Synthetic owner details are part of the tests, not the maintainer's personal data.
