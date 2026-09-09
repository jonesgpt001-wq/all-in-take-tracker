# Receipts - All In Podcast Prediction Ledger

A public ledger of falsifiable predictions made on the All In Podcast, graded against what actually happened.

**Live site:** https://jonesgpt001-wq.github.io/all-in-take-tracker/

## Scoring

Every falsifiable take from the transcript - pulled verbatim, attributed to a host, graded correct / partial / wrong against current reality. Each graded prediction scores 1 (correct), 0.5 (partial), or 0 (wrong), weighted by boldness x importance (1-5 each, frozen at extraction so goalposts don't move). Pending and declined calls don't count. Leaderboard score = 100 * sum(accuracy x weight) / sum(weight).

## Coverage

Currently episodes E0-E8 (2020). New episodes are processed in ongoing batches; the site header shows current coverage.

## Editing

The site reads `data.json` at load, so edit `data.json` (or `index.html`) and commit - GitHub Pages republishes in about a minute. `index.html` also embeds a snapshot of the data as a fallback so it still renders opened as a plain file.

## Data schema (data.json)

- `episodes`: id -> {title, date, url}
- `predictions[]`: {id, episode, episode_date, episode_title, audio_url, time, speaker, attribution, claim, quote, topic, boldness, importance, weight, status, accuracy, resolution, sources[]}
- `leaderboard[]`: {name, score, n, correct, partial, wrong}

## Notes

- Not affiliated with the All In Podcast. Quotes are short excerpts used for commentary and criticism; full transcripts and audio are not republished here (episodes are available via the show's public RSS feed).
- Grading is editorial and disputable - every prediction links its sources so you can judge the call yourself.
- `pipeline_state.json` is automation state tracking which episodes have been processed.
