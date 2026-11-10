---
name: slate-research
description: Gives a short research brief for one DFS slate or one game (NBA, NFL, NHL, MLB, WNBA, PGA, UFC, LoL) from the BankrollSZN connector - games, totals, injuries, top projections, chalk, leverage and key matchups. Use when the user asks what to know about tonight's slate, a game preview, who to target, or a slate breakdown.
---

# Slate research

Give a short brief for one slate or one game. Every number must come from a tool call in this chat. Do not estimate a number.

## Steps

1. **Slate.** Call the sport's `*_list_slates` tool and pick the slate the user names, or the main slate.
2. **Games and totals.** Call `odds_comparison` (or `mlb_game_odds` for MLB, `mma_odds` for UFC) for game totals, spreads and moneylines.
3. **News.** Call the sport's injury tool. For NBA, also call `nba_rotations`. For NHL, call `nhl_starting_goalies` and `nhl_lines`. For MLB, call `mlb_starters` and `mlb_weather`. For NFL, call `nfl_weather` and `nfl_injury_vacancy`.
4. **Projections and ownership.** Call the sport's projections tool. For contest-type ownership, call the sport's `*_ownership_by_contest` tool if it exists.
5. **Matchups.** Call the sport's matchup tool (for example `nba_matchup`, `nfl_game_matchup`, `nhl_team_matchups`, `mlb_matchup`, `mma_matchups`). For MLB stacks, call `mlb_team_stacks`. For NFL stacks, call `nfl_team_stacks`.

## Output

Keep it short. Use these headings:

1. **Games to target.** The two or three games with the best environment, with totals.
2. **News that changes the slate.** Outs, starters and role changes.
3. **Top plays by position.** Projection, salary and ownership.
4. **Leverage.** Two or three lower-owned plays with upside, and why.
5. **Fades.** One or two popular plays with risk, and why.

End with this line: "For research and entertainment only, not financial advice. 18+ (21+ where required). Gambling problem? Call 1-800-GAMBLER."
