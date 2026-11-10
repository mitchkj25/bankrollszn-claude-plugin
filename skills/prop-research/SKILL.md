---
name: prop-research
description: Compares market player prop lines and game lines to BankrollSZN projections and sims (NBA, NFL, MLB, NHL, UFC, PGA), with best available price and line movement. Use when the user asks about a player prop, the biggest projection gaps, over or under on a stat, best price for a line, or the BankrollSZN model picks.
---

# Prop research

Compare the market to the BankrollSZN projection. Every number must come from a tool call in this chat. Do not estimate a number. This skill gives research. It does not place bets.

## Steps

1. **Props.** Call the sport's props tool: `nba_props`, `nfl_props`, `mlb_props` or `nhl_odds_props`. Pass `player` when the user names a player. Pass `sort_by` `edge` for the biggest gaps.
2. **Price.** Call `best_price` or `odds_comparison` to show the best available price across books.
3. **Movement.** Call the sport's `*_line_movement` tool to show how the line moved.
4. **Model picks.** When the user asks for picks, call the sport's `*_sim_picks` tool. Show the graded record that the tool returns next to the picks.
5. **Context.** Call the sport's injury tool, and the matchup tool for the player's game, to explain the gap.

## Output

- A table: player, market, line, over and under odds, no-vig over probability, BankrollSZN projection and the gap.
- One line per row on why the gap exists (role, matchup, minutes, weather).
- Say plainly when the gap is small or the sample is thin.

## Rules

- Do not say a bet is certain or "a lock".
- Do not promise a profit.
- End with this line: "For research and entertainment only, not financial advice. 18+ (21+ where required). Gambling problem? Call 1-800-GAMBLER."
