---
name: dfs-lineup-builder
description: Builds DraftKings DFS lineups (GPP or cash, classic or showdown) for NBA, NFL, NHL, MLB, WNBA, PGA, UFC or LoL from the BankrollSZN connector, with every number taken from a tool call. Use when the user asks for DFS lineups, a 20-max or 150-max build, a single-entry lineup, a cash lineup or a DraftKings upload file.
---

# DFS lineup builder

Build DraftKings lineups with the BankrollSZN connector. Every number in the answer must come from a tool call in this chat. Do not estimate a number. If a tool returns nothing, say so and name the tool.

## Steps

1. **Find the slate.** Call the sport's `*_list_slates` tool (for example `nba_list_slates`). Use the main slate unless the user names another slate or a showdown game. PGA uses `pga_schedule`. UFC uses `mma_list_slates`.
2. **Check news.** Call the sport's injury tool (`nba_injuries`, `nfl_injuries`, `nhl_injuries`, `mma_late_changes`, `pga_injury_watch`). For NHL, also call `nhl_starting_goalies`. For MLB, call `mlb_starters` and `mlb_postponements`. Leave out players who are out.
3. **Set the contest type.** Use the type the user names (`20max`, `150max`, `3max`, `single`). If the user names none, use `20max` and say so. Pass the same contest type to the projection, ownership and optimizer tools so the ownership matches the contest.
4. **Read the pool.** Call the sport's projections or player pool tool for the same slate. Note the top values, the chalk and the low-owned upside plays.
5. **Build.** Call the sport's optimizer (for example `nba_optimizer`, `nfl_optimizer`, `nfl_showdown_optimizer`, `mlb_optimizer`). Pass the user's locks, excludes, stacks and exposure caps. Use the lineup count the user asks for. If the result has `next_call`, call the optimizer again with its arguments until `remaining` is 0.
6. **Check the roster rules.** Confirm each lineup is under the $50,000 cap and fills every slot. In NFL classic, do not roster a DST against the user's own QB. In NHL classic, use skaters from at least 3 teams.

## Output

- A short table per lineup: slot, player, team, salary, projection and projected ownership.
- Totals per lineup: salary, projection and ownership.
- Two or three lines on the build logic: the stacks, the leverage plays and the main risks.
- If the optimizer returns a `csv` field, give it to the user as the DraftKings upload file.

## Rules

- Do not invent a player, a salary or a projection.
- Name each player who is questionable.
- End with this line: "For research and entertainment only, not financial advice. 18+ (21+ where required). Gambling problem? Call 1-800-GAMBLER."
