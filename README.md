# EFL Championship 2026-27 Tracker

A static tracker for the second tier of English football, mirroring the Premier League tracker, with three tabs:
- **League Table**: full standings, color-coded by automatic promotion (1-2), play-off zone (3-6), and relegation zone (22-24), plus a "Promotion Race" view and a "Relegation Watch" view of what each bottom-table team needs to reach safety.
- **Club Stats**: clean sheets, home/away form splits, biggest wins & heaviest losses — all derived from match results.
- **Player Stats**: Golden Boot race, plus expandable lists for Most Goals, Most Assists, and Most Goals & Assists.

## Data source
[football-data.org](https://www.football-data.org/) free API (Championship competition code `ELC`).

Unlike the companion Premier League tracker, no working free source for Championship cards or individual goalkeeper clean sheets has been found — the Premier League's own public stats API (pulselive) lists the Championship but returns no populated player stats for it. Assists also aren't populated by football-data.org for this competition, so the "Most Assists" list currently falls back to goal-sorted order (flagged in the page itself).

## Regenerating

```bash
export FOOTBALL_DATA_API_TOKEN=your_token_here
./fetch_data.sh
git add index.html
git commit -m "Refresh standings"
git push
```

Not live-updating — rebuild after each matchday (or whenever) to refresh the table.
