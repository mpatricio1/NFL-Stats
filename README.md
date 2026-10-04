# NFL 2026 Stat Sheet

Advanced stats for all 32 NFL teams in the 2026 season: EPA and success rate, NFL Next Gen Stats, FTN DVOA and charting, PFR pressure, coverage and broken tackles, snap-count personnel, and special teams.

Open `index.html` (or the GitHub Pages site). Pick a team from the menu at the top, or link straight to one with `#TEAM`, for example `#NE`, `#KC`, `#LA`. The Home/Away buttons switch between each team's home and away colors.

The page is a single self-contained file with the data built in; the only outside request is Google Fonts. It is rebuilt every Wednesday with the latest completed week.

Sources: nflverse (play-by-play, Next Gen Stats, FTN charting, PFR advanced stats, snap counts, rosters), FTN's weekly DVOA ratings, Pro Football Reference. Full notes are in the page's "Sources & method" section.

## Data files

The same data is published as plain files for anyone (or any tool) that can't run JavaScript: [`data/`](data/) has a no-JavaScript index with every team's key numbers, `team_summary.csv` (one row per team), per-table CSVs, the full `data.json`, and column notes in `data/README.md`. [`llms.txt`](llms.txt) points AI agents to them. On the live site: https://mpatricio1.github.io/NFL-Stats/data/ . They're regenerated with the page each week.
