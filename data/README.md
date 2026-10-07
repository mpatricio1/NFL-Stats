# NFL 2026 Stat Sheet data (through Week 3)

Plain-file copy of the data behind https://mpatricio1.github.io/NFL-Stats/ , rebuilt every Wednesday with the page. Data as of 2026-10-02.
Sources: nflverse (play-by-play EPA, Next Gen Stats, FTN charting, PFR advanced stats, snap counts, rosters) and FTN's weekly DVOA ratings.

## Files

- [data.json](data.json): The full dataset the page is drawn from (every file listed here, plus team colors and per-team detail)
- [team_summary.csv](team_summary.csv): One row per team: record, points, EPA/play and success rate (offense, defense, pass, rush) with ranks, FTN DVOA, broken tackles, pressure, coverage allowed, FTN charting rates, average personnel on the field, accepted penalties, presnap motion (32 rows)
- [dvoa.csv](dvoa.csv): FTN DVOA ratings through Week 3 (total, offense, defense, special teams, with ranks) (32 rows)
- [team_efficiency.csv](team_efficiency.csv): Team EPA, success rate, points and ranks (also inside team_summary.csv) (32 rows)
- [qbs.csv](qbs.csv): Quarterbacks: EPA per dropback, CPOE, success rate, sack rate, NGS time to throw and aggressiveness (q = meets NGS qualifier) (39 rows)
- [rushers.csv](rushers.csv): Rushers league-wide: carries, yards, EPA per carry, success rate, NGS rush yards over expected (52 rows)
- [receivers_ngs.csv](receivers_ngs.csv): Receivers and TEs league-wide (NGS qualifiers): targets, separation, YAC over expected, intended air yards (105 rows)
- [qb_pressure_to_sack.csv](qb_pressure_to_sack.csv): QB pressures, sacks and pressure-to-sack rate (PFR) (39 rows)
- [broken_tackles_team.csv](broken_tackles_team.csv): Broken tackles by team (PFR, rushing + receiving), per game and rank (32 rows)
- [broken_tackles_leaders.csv](broken_tackles_leaders.csv): Broken tackle leaders (PFR) (10 rows)
- [personnel_avg_on_field.csv](personnel_avg_on_field.csv): Average players on the field per snap by position (from snap counts) (32 rows)
- [motion_team.csv](motion_team.csv): Presnap motion by team (FTN is_motion + pbp EPA): motion rate and EPA/play, yards/play, success rate with (_m) and without (_n) motion, all plays / pass_ / run_, offense (o_) and defense faced (d_), with ranks (32 rows)
- [penalties_team.csv](penalties_team.csv): Accepted penalties by team: count and yards, split offense/defense/special teams, first downs given by defensive fouls; per game and rank (1 = fewest) (32 rows)
- [ftn_offense.csv](ftn_offense.csv): FTN charting rates, offense: play action, motion, interceptable throws, drops, blitzes faced, out of pocket, screens (32 rows)
- [ftn_defense.csv](ftn_defense.csv): FTN charting rates, defense (same columns, as faced/allowed) (32 rows)
- [team_games.csv](team_games.csv): Game log: opponent, score, EPA, success rate, yards, turnovers (all 32 teams, team column) (96 rows)
- [team_pa_split.csv](team_pa_split.csv): Play action vs. not: EPA per dropback (all 32 teams, team column) (64 rows)
- [team_blitz.csv](team_blitz.csv): Blitzed vs. not: EPA per dropback (all 32 teams, team column) (64 rows)
- [team_qb_ngs.csv](team_qb_ngs.csv): NGS passing by week (week 0 = season) (all 32 teams, team column) (135 rows)
- [team_rushers.csv](team_rushers.csv): Team rushers: carries, yards, EPA, success rate, RYOE (all 32 teams, team column) (84 rows)
- [team_rush_pfr.csv](team_rush_pfr.csv): Yards before and after contact (PFR) (all 32 teams, team column) (176 rows)
- [team_bt_players.csv](team_bt_players.csv): Broken tackles by player (PFR) (all 32 teams, team column) (412 rows)
- [team_lanes.csv](team_lanes.csv): Run results by gap/lane (all 32 teams, team column) (236 rows)
- [team_rec.csv](team_rec.csv): Receiving: targets, share, EPA/target, separation, YAC over expected (all 32 teams, team column) (293 rows)
- [team_snaps.csv](team_snaps.csv): Snap counts and shares, offense and defense (all 32 teams, team column) (1680 rows)
- [team_defense.csv](team_defense.csv): Defenders: snaps, coverage allowed, pressures, missed tackles, tackles, sacks (all 32 teams, team column) (632 rows)
- [team_st.csv](team_st.csv): Special teams: kicking, punting, returns (all 32 teams, team column) (163 rows)
- [team_sacks.csv](team_sacks.csv): Every sack taken, with FTN context (rushers, blitzers, QB fault) and bucket (all 32 teams, team column) (212 rows)
- [team_backs.csv](team_backs.csv): Offense by backs in the backfield (FTN), with league comparison (all 32 teams, team column) (96 rows)
- [team_box_off.csv](team_box_off.csv): Designed runs by defenders in the box (FTN), with league comparison (all 32 teams, team column) (96 rows)
- [team_box_def.csv](team_box_def.csv): Run defense by box count (FTN), with league comparison (all 32 teams, team column) (96 rows)
- [team_rush_def.csv](team_rush_def.csv): Pass defense by number of pass rushers (FTN), with league comparison (all 32 teams, team column) (96 rows)
- [team_penalty_players.csv](team_penalty_players.csv): Accepted penalties by player and page section (QB, RB, WR incl. TE, OL, FRONT, DB; ST = any flag on a kick or punt) (all 32 teams, team column) (465 rows)
- [team_penalties_by_group.csv](team_penalties_by_group.csv): Accepted penalties by page section: flags, yards and per-game rank among 32 teams, 1 = fewest (TEAM = no player named) (all 32 teams, team column) (288 rows)
- [penalties.csv](penalties.csv): Every accepted foul: game, week, team, phase (off/def/st), type, yards, player, roster position, page section (692 rows)
- [team_coverage_by_group.csv](team_coverage_by_group.csv): Coverage allowed by position group (CB, S, LB, Edge/DL), PFR (all 32 teams, team column) (126 rows)
- [commentary.csv](commentary.csv): Hand-written team write-ups, one row per team and section (384 rows)
- [commentary.md](commentary.md): The same write-ups as one readable Markdown file (384 rows)

## Columns in team_summary.csv

- `team`: nflverse abbreviation (LA = Rams, LAC = Chargers, LV = Raiders).
- `off_epa`, `def_epa`: expected points added per play (nflverse play-by-play). Higher is better on offense; lower (more negative) is better on defense.
- `off_sr`, `def_sr`: success rate, share of plays with positive EPA.
- `*_pass_epa`, `*_rush_epa`: the same split by pass (per dropback, sacks included) and designed run.
- `proe`: pass rate over expected, in percentage points.
- `sack_rate`, `def_sack_rate`: sacks per dropback, taken and made.
- `pf`, `pa`, `w`, `l`, `t`, `gp`, `pt_diff`, `pf_pg`, `pa_pg`: points and record.
- Any column ending `_rk` is a rank out of 32 where 1 is best (for defense, 1 is the stingiest).
- `dvoa_*`: FTN DVOA, percent better (+) or worse (-) than average, adjusted for situation and opponent. Negative defensive DVOA is good.
- `bt`, `bt_pg`, `bt_rk`: broken tackles by the team's ball carriers (PFR), total, per game and rank.
- `pressure_*`, `pressures_pg`: pressures generated by the defense (PFR).
- `cov_allowed_*`: passing allowed in coverage, per PFR charting (can exceed actual passing yards).
- `ftn_off_*`, `ftn_def_*`: FTN charting rates (share of dropbacks or plays) and counts.
- `avg_on_field_*`: average number of players at each position per snap.
- `penalties_*`: accepted penalties committed by the team (nflverse play-by-play; declined and offsetting fouls excluded). `n`, `yds`, `off_n`, `def_n`, `st_n` (flags on kicks and punts), `fd` (first downs given by defensive fouls), each with `_pg` per game and `_rk`, where 1 is fewest.
- `motion_*`: presnap motion (FTN charting, every pass and run play). `o_` offense, `d_` defense faced; `pass_` / `run_` split by dropbacks and designed runs. `rate` = share of plays with motion (`_rk` 1 = most). `epa_m` / `epa_n`, `ypp_m` / `ypp_n`, `sr_m` / `sr_n` = EPA per play, yards per play and success rate with and without motion; `gain` = `epa_m` minus `epa_n`. `n` plays, `n_m` plays with motion. EPA ranks: 1 is best.
